[문제 바로가기](https://boj.kr/22114)

```c++
#include <bits/stdc++.h>

using namespace std;

int blk[100001];
int dp[100001][2];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < N - 1; i++){
        cin >> blk[i];
    }

    dp[0][0] = 1;
    dp[0][1] = 1;
    for(int i = 0; i < N; i++){
        if(blk[i - 1] <= K) {
            dp[i][0] = dp[i - 1][0] + 1;
            dp[i][1] = dp[i - 1][1] + 1;
        }else{
            dp[i][0] = 1;
            dp[i][1] = dp[i - 1][0] + 1;
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        ans = max(dp[i][0], ans);
        ans = max(dp[i][1], ans);
    }

    cout << ans << "\n";

    return 0;
}
```