[문제 바로가기](https://boj.kr/1937)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[501][501];
int dp[501][501];
int N;

int dfs(int curX, int curY){
    if(dp[curX][curY] != 0){
        return dp[curX][curY];
    }

    dp[curX][curY] = 1;
    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    for(int i = 0; i < 4; i++){
        int newX = curX + dx[i];
        int newY = curY + dy[i];

        if(newX < 0 || newX >= N || newY < 0 || newY >= N){
            continue;
        }

        if(arr[curX][curY] < arr[newX][newY]){
            dp[curX][curY] = max(dfs(newX, newY) + 1, dp[curX][curY]);
        }
    }

    return dp[curX][curY];
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> arr[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            ans = max(dfs(i, j), ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```