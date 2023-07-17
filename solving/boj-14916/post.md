[문제 바로가기](https://boj.kr/14916)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = -1;
    dp[2] = 1;
    dp[3] = -1;
    dp[4] = 2;
    dp[5] = 1;

    for(int i = 6; i <= N; i++){
        dp[i] = min(dp[i - 2], dp[i - 5]) + 1;
    }

    cout << dp[N] << "\n";

    return 0;
}
```