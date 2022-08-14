[문제 바로가기](https://boj.kr/2748)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[100];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[0] = 0;
    dp[1] = 1;

    for(int i = 2; i <= N; i++){
        dp[i] = dp[i - 1] + dp[i - 2];
    }

    cout << dp[N] << "\n";

    return 0;
}
```