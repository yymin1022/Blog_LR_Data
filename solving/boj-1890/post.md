[문제 바로가기](https://boj.kr/1890)

```c++
#include  <bits/stdc++.h>

using namespace std;

int N;
int board[101][101];
long long dp[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> board[i][j];
        }
    }

    dp[0][0] = 1;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(board[i][j]){
                int newX = i + board[i][j];
                int newY = j + board[i][j];

                if(newX < N){
                    dp[newX][j] += dp[i][j];
                }

                if(newY < N){
                    dp[i][newY] += dp[i][j];
                }
            }
        }
    }

    cout << dp[N - 1][N - 1] << "\n";

    return 0;
}
```