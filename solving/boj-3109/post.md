[문제 바로가기](https://boj.kr/3109)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[10001][501];
char board[10001][501];
int R, C;

int dfs(int x, int y){
    if(y == C - 1){
        return 1;
    }

    int dx[3] = {-1, 0, 1};
    for(int i = 0; i < 3; i++){
        int newX = x + dx[i];
        int newY = y + 1;

        if(newX < 0 || newX >= R || newY < 0 || newY >= C){
            continue;
        }

        if(board[newX][newY] != 'x' && !isVisit[newX][newY]){
            isVisit[newX][newY] = true;

            if(dfs(newX, newY)){
                return 1;
            }
        }
    }

    return 0;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> R >> C;

    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            cin >> board[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < R; i++){
        ans += dfs(i, 0);
    }

    cout << ans << "\n";

    return 0;
}
```