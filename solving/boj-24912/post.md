[문제 바로가기](https://boj.kr/24912)

```c++
#include <bits/stdc++.h>

using namespace std;

int card[1000001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> idx;
    for(int i = 0; i < N; i++){
        cin >> card[i];

        if(card[i] == 0){
            idx.push_back(i);
        }
    }

    for(int i = 1; i < N; i++){
        if(card[i] > 0 && card[i] == card[i - 1]){
            cout << -1 << "\n";
            return 0;
        }
    }

    for(int i = 0; i < idx.size(); i++){
        for(int j = 1; j <= 3; j++){
            if(card[idx[i] - 1] != j && card[idx[i] + 1] != j){
                card[idx[i]] = j;
                break;
            }
        }
    }

    for(int i = 0; i < N; i++){
        cout << card[i] << " ";
    }

    return 0;
}
```