[문제 바로가기](https://boj.kr/26169)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isAble;
bool isVisit[5][5];
int board[5][5];

void dfs(int R, int C, int cnt, int move){
    if(board[R][C] == 1){
        cnt++;
    }

    if(cnt >= 2 && move == 3){
        isAble = true;
        return;
    }

    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    for(int i = 0; i < 4; i++){
        int newX = R + dx[i];
        int newY = C + dy[i];

        if(newX < 0 || newX >= 5 || newY < 0 || newY >= 5 || board[newX][newY] < 0){
            continue;
        }

        if(!isVisit[newX][newY]){
            isVisit[newX][newY] = true;
            dfs(newX, newY, cnt, move + 1);
            isVisit[newX][newY] = false;
        }
    }
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 5; i++){
        for(int j = 0; j < 5; j++){
            cin >> board[i][j];
        }
    }

    int R, C;
    cin >> R >> C;

    isVisit[R][C] = true;
    dfs(R, C, 0, 0);

    cout << (isAble ? 1 : 0) << "\n";

    return 0;
}
```