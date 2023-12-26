[문제 바로가기](https://boj.kr/13699)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[40];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[0] = 1;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= i; j++){
            dp[i] += dp[j - 1] * dp[i - j];
        }
    }

    cout << dp[N] << "\n";

    return 0;
}
```