[문제 바로가기](https://boj.kr/1520)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dfs(int, int);

int N, M;
int dp[501][501];
int height[501][501];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> height[i][j];
            dp[i][j] = -1;
        }
    }

    cout << dfs(0, 0) << "\n";

    return 0;
}

int dfs(int x, int y){
    if(x == N - 1 && y == M - 1){
        return 1;
    }

    if(dp[x][y] < 0){
        dp[x][y] = 0;

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = x + dx[i];
            int newY = y + dy[i];

            if(newX >= 0 && newX < N && newY >= 0 && newY < M && height[x][y] > height[newX][newY]){
                dp[x][y] += dfs(newX, newY);
            }
        }
    }

    return dp[x][y];
}
```