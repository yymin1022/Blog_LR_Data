[문제 바로가기](https://boj.kr/2225)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[201][201];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 1; i <= K; i++){
        dp[0][i] = 1;
    }

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= K; j++){
            dp[i][j] = (dp[i - 1][j] + dp[i][j - 1]) % 1000000000;
        }
    }

    cout << dp[N][K] << "\n";

    return 0;
}
```