[문제 바로가기](https://boj.kr/14606)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[11];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 0;
    dp[2] = 1;
    for(int i = 3; i <= N; i++){
        int tmp = i / 2;
        dp[i] = (tmp * (i - tmp)) + dp[i - tmp] + dp[tmp];
    }

    cout << dp[N] << "\n";

    return 0;
}
```