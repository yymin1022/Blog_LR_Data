[문제 바로가기](https://boj.kr/2133)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[31];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[0] = 1;
    dp[2] = 3;

    for(int i = 4; i <= N; i += 2){
        for(int j = 0; j < i - 2; j++){
            dp[i] += dp[j] * 2;
        }
        dp[i] += dp[i - 2] * 3;
    }

    cout << dp[N] << "\n";

    return 0;
}
```