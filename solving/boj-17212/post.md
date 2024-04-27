[문제 바로가기](https://boj.kr/17212)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 1;
    dp[3] = 2;
    dp[4] = 2;
    dp[5] = 1;
    dp[6] = 2;
    dp[7] = 1;
    for(int i = 8; i <= N; i++){
        dp[i] = 100001;
        dp[i] = min(dp[i - 1] + 1, dp[i]);
        dp[i] = min(dp[i - 2] + 1, dp[i]);
        dp[i] = min(dp[i - 5] + 1, dp[i]);
        dp[i] = min(dp[i - 7] + 1, dp[i]);
    }

    cout << dp[N] << "\n";

    return 0;
}
```