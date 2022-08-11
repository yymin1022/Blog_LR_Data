[문제 바로가기](https://boj.kr/9655)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 2;

    for(int i = 3; i <= N; i++){
        dp[i] = min(dp[i - 1] + 1, dp[i - 3] + 3);
    }

    cout << (dp[N] % 2 ? "SK" : "CY") << "\n";

    return 0;
}
```