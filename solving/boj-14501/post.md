[문제 바로가기](https://boj.kr/14501)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[20];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int T, P;
        cin >> T >> P;

        dp[i + 1] = max(dp[i], dp[i + 1]);
        dp[i + T] = max(dp[i] + P, dp[i + T]);
    }

    cout << dp[N] << "\n";

    return 0;
}
```