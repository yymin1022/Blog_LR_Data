[문제 바로가기](https://boj.kr/1987)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int, int, int);

bool isVisit[26];
char board[20][20];
int ans;
int R, C;

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

    isVisit[board[0][0] - 'A'] = true;
    dfs(0, 0, 1);

    cout << ans << "\n";

    return 0;
}

void dfs(int curX, int curY, int cnt){
    ans = max(cnt, ans);

    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    for(int i = 0; i < 4; i++){
        int newX = curX + dx[i];
        int newY = curY + dy[i];

        if(newX >= 0 && newX < R && newY >= 0 && newY < C){
            char newC =board[newX][newY];
            if(!isVisit[newC - 'A']){
                isVisit[newC - 'A'] = true;
                dfs(newX, newY, cnt + 1);
                isVisit[newC - 'A'] = false;
            }
        }
    }
}
```