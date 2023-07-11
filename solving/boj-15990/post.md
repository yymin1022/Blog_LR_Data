[문제 바로가기](https://boj.kr/15990)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001][4];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    dp[1][1] = 1;
    dp[2][2] = 1;
    dp[3][1] = 1;
    dp[3][2] = 1;
    dp[3][3] = 1;

    for(int i = 4; i <= 100000; i++){
        dp[i][1] = (dp[i - 1][2] + dp[i - 1][3]) % 1000000009;
        dp[i][2] = (dp[i - 2][1] + dp[i - 2][3]) % 1000000009;
        dp[i][3] = (dp[i - 3][1] + dp[i - 3][2]) % 1000000009;
    }

    while(T--){
        int N;
        cin >> N;

        cout << ((long long)dp[N][1] + (long long)dp[N][2] + (long long)dp[N][3]) % 1000000009 << "\n";
    }

    return 0;
}
```