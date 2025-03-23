[문제 바로가기](https://boj.kr/17845)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001][10001];
int I[10001];
int T[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 1; i <= K; i++){
        cin >> I[i] >> T[i];
    }

    int ans = 0;
    for(int i = 1; i <= K; i++){
        for(int j = 1; j <= N; j++){
            if(j - T[i] >= 0){
                dp[i][j] = max(dp[i - 1][j], dp[i - 1][j - T[i]] + I[i]);
            }else{
                dp[i][j] = dp[i - 1][j];
            }

            ans = max(dp[i][j], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```
