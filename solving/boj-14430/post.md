[문제 바로가기](https://boj.kr/14430)

```c++
#include <bits/stdc++.h>

using namespace std;

int area[301][301];
int dp[301][301];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> area[i][j];
        }
    }

    dp[0][0] = area[0][0];
    int dx[2] = {0, -1};
    int dy[2] = {-1, 0};
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(i == 0 && j == 0){
                continue;
            }

            for(int k = 0; k < 2; k++){
                int nx = i + dx[k];
                int ny = j + dy[k];

                if(nx < 0 || ny < 0){
                    continue;
                }

                dp[i][j] = max(dp[nx][ny] + area[i][j], dp[i][j]);
            }
        }
    }

    cout << dp[N - 1][M - 1] << "\n";

    return 0;
}

```