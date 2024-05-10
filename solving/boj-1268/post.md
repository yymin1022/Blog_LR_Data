[문제 바로가기](https://boj.kr/1268)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[1001][5];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < 5; j++){
            cin >> arr[i][j];
        }
    }

    set<int> data[1001];
    for(int i = 0; i < 5; i++){
        for(int j = 0; j < N; j++){
            for(int k = 0; k < N; k++){
                if(j != k && arr[j][i] == arr[k][i]){
                    data[j].insert(k);
                }
            }
        }
    }

    int ansIdx = 0;
    int ansVal = 0;
    for(int i = 0; i < N; i++){
        if(data[i].size() > ansVal){
            ansIdx = i;
            ansVal= data[i].size();
        }
    }

    cout << ansIdx + 1 << "\n";

    return 0;
}
```