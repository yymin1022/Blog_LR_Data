[문제 바로가기](https://boj.kr/1915)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        for(int j = 0; j < M; j++){
            dp[i][j] = S[j] - '0';
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(i > 0 && j > 0 && dp[i][j]){
                dp[i][j] = min(dp[i - 1][j - 1], min(dp[i - 1][j], dp[i][j - 1])) + 1;
            }
            ans = max(dp[i][j], ans);
        }
    }

    cout << ans * ans << "\n";

    return 0;
}
```