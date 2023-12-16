[문제 바로가기](https://boj.kr/14494)

```c++
#include  <bits/stdc++.h>

using namespace std;

long long dp[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    dp[1][1] = 1;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= M; j++){
            if(i == 1 && j == 1){
                continue;
            }
            dp[i][j] = (dp[i][j - 1] + dp[i - 1][j] + dp[i - 1][j - 1]) % 1000000007;
        }
    }

    cout << dp[N][M] << "\n";

    return 0;
}
```