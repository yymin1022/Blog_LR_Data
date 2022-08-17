[문제 바로가기](https://boj.kr/11057)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001][10];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < 10; i++){
        dp[1][i] = 1;
    }

    for(int i = 2; i <= N; i++){
        for(int j = 0; j < 10; j++){
            for(int k = 0; k <= j; k++){
                dp[i][j] += dp[i - 1][k];
            }
            dp[i][j] %= 10007;
        }
    }

    int ans = 0;
    for(int i = 0; i < 10; i++){
        ans += dp[N][i];
    }

    cout << ans % 10007 << "\n";

    return 0;
}
```