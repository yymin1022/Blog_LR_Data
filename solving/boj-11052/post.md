[문제 바로가기](https://boj.kr/11052)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[10001];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> P(N + 1);
    for(int i = 1; i <= N; i++){
        cin >> P[i];
    }

    dp[1] = P[1];
    for(int i = 2; i <= N; i++){
        dp[i] = P[i];
        for(int j = 1; j < i; j++){
            dp[i] = max(dp[j] + dp[i - j], dp[i]);
        }
    }

    cout << dp[N] << "\n";

    return 0;
}
```