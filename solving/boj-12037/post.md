[문제 바로가기](https://boj.kr/12037)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[16][2];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int C, V, L;
        cin >> C >> V >> L;

        dp[0][0] = C;
        dp[0][1] = V;
        for(int i = 1; i < L; i++){
            dp[i][0] = dp[i - 1][1] * C % 1000000007;
            dp[i][1] = (dp[i - 1][0] + dp[i - 1][1]) * V % 1000000007;
        }

        cout << "Case #" << t << ": ";
        cout << dp[L - 1][1] << "\n";
    }

    return 0;
}
```
