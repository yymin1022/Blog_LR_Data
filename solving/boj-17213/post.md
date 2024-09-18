[문제 바로가기](https://boj.kr/17213)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[31][31];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    dp[0][0] = 1;
    for(int i = 1; i < 31; i++) {
        dp[i][0] = 1;

        for(int j = 1; j <= i; j++){
            dp[i][j] = dp[i - 1][j - 1] + dp[i - 1][j];
        }
    }

    int N, M;
    cin >> N >> M;

    cout << dp[M - 1][N - 1];

    return 0;
}

```
