[문제 바로가기](https://boj.kr/9084)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[10001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        memset(dp, 0, sizeof(dp));
        vector<int> coins;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            coins.push_back(input);
        }

        int M;
        cin >> M;

        dp[0] = 1;
        for(int i = 0; i < N; i++){
            for(int j = coins[i]; j <= M; j++){
                dp[j] += dp[j - coins[i]];
            }
        }

        cout << dp[M] << "\n";
    }

    return 0;
}
```