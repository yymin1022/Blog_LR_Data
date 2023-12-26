[문제 바로가기](https://boj.kr/16395)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[31][31];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i <= 30; i++){
        dp[i][0] = 1;
    }

    for(int i = 1; i <= 30; i++){
        for(int j = 1; j <= i; j++){
            dp[i][j] = dp[i - 1][j - 1] + dp[i - 1][j];
        }
    }

    int N, K;
    cin >> N >> K;
    cout << dp[N - 1][K - 1] << '\n';

    return 0;
}
```