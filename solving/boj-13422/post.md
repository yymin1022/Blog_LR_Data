[문제 바로가기](https://boj.kr/13422)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, M, K;
        cin >> N >> M >> K;

        vector<int> house;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            house.push_back(input);
        }

        if(N == M){
            int money = 0;
            for(int i = 0; i < M; i++){
                money += house[i];
            }

            if(money < K){
                cout << 1 << "\n";
                continue;
            }
        }

        int ans = 0;
        int money = 0;
        for(int i = 0; i < N; i++){
            if(!i){
                for(int j = 0; j < M; j++){
                    money += house[i + j];
                }
            }else{
                money -= house[i - 1];
                money += house[(i - 1 + M >= N) ? i - 1 + M - N : i - 1 + M];
            }

            if(money < K){
                ans++;
            }
        }

        cout << ans << "\n";
    }
}
```