[문제 바로가기](https://boj.kr/10048)

```c++
#include  <bits/stdc++.h>

using namespace std;

int N, M;
int candy[1001][1001];
int dp[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> candy[i][j];
            dp[i][j] = -1;
        }
    }

    dp[0][0] = candy[0][0];

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(dp[i][j] < 0){
                dp[i][j] = candy[i][j];

                int dx[3] = {-1, 0, -1};
                int dy[3] = {0, -1, -1};
                for(int k = 0; k < 3; k++){
                    int newX = i + dx[k];
                    int newY = j + dy[k];

                    if(newX >= 0 && newX < N && newY >= 0 && newY < M){
                        dp[i][j] = max(dp[newX][newY] + candy[i][j], dp[i][j]);
                    }
                }
            }
        }
    }

    cout << dp[N - 1][M - 1];

    return 0;
}
```