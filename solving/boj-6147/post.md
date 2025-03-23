[문제 바로가기](https://boj.kr/6147)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, B;
    cin >> N >> B;

    vector<int> cow;
    for(int i = 0; i < N; i++){
        int H;
        cin >> H;
        cow.push_back(H);
    }

    sort(cow.begin(), cow.end(), greater<int>());

    int height = 0;
    for(int i = 0; i < N; i++){
        if(height >= B){
            cout << i << "\n";
            return 0;
        }else{
            height += cow[i];
        }
    }

    return 0;
}

```