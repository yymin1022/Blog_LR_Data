[문제 바로가기](https://boj.kr/11051)

```c++
#include <bits/stdc++.h>
using namespace std;

int dp[1005][1005];

int main () {
    cin.tie(NULL);
    cout.tie(NULL);
    ios::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    dp[0][0] = 1;
    dp[0][1] = 0;
    for (int i = 1; i <= N; i++) {
        for(int j = 0; j <= i; j++) {
            dp[i][j] = (dp[i-1][j] + dp[i-1][j-1]) % 10007;
        }
    }

    cout << dp[N][K];

    return 0;
}```