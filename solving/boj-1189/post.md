[문제 바로가기](https://boj.kr/1189)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[10][10];
char board[10][10];

int R, C, K, ans;

void dfs(int curX, int curY, int cnt){
    if(cnt > K){
        return;
    }

    if(cnt == K && curX == 0 && curY == C - 1){
        ans++;
        return;
    }

    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    for(int i = 0; i < 4; i++){
        int newX = curX + dx[i];
        int newY = curY + dy[i];

        if(newX < 0 || newX >= R || newY < 0 || newY >= C){
            continue;
        }

        if(board[newX][newY] == '.' && !isVisit[newX][newY]){
            isVisit[newX][newY] = true;
            dfs(newX, newY, cnt + 1);
            isVisit[newX][newY] = false;
        }
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> R >> C >> K;

    for(int i = 0; i < R; i++){
        string input;
        cin >> input;
        for(int j = 0; j < C; j++){
            board[i][j] = input[j];
        }
    }

    isVisit[R - 1][0] = true;
    dfs(R - 1, 0, 1);

    cout << ans << "\n";

    return 0;
}
```