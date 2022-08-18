[문제 바로가기](https://boj.kr/1699)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        dp[i] = i;
    }

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= sqrt(i); j++){
            dp[i] = min(dp[i - j * j] + 1, dp[i]);
        }
    }

    cout << dp[N] << "\n";

    return 0;
}
```