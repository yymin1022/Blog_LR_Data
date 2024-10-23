[문제 바로가기](https://boj.kr/7348)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[201];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int TC;
    cin >> TC;

    while(TC--){
        memset(dp, 0, sizeof(dp));
        int N;
        cin >> N;

        int ans = 0;
        for(int i = 0; i < N; i++){
            int S, T;
            cin >> S >> T;

            if(S > T){
                swap(S, T);
            }

            S = (S - 1) / 2;
            T = (T - 1) / 2;

            for(int j = S; j <= T; j++){
                dp[j] += 10;
                ans = max(dp[j], ans);
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```