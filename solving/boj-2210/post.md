[문제 바로가기](https://boj.kr/2210)

```c++
#include  <bits/stdc++.h>

using namespace std;

int board[5][5];
set<int> ans;

void dfs(int curX, int curY, int num, int depth){
    if(depth == 5){
        ans.insert(num);
        return;
    }

    int dx[4] = {0, 1, 0, -1};
    int dy[4] = {1, 0, -1, 0};
    for(int i = 0; i < 4; i++){
        int newX = curX + dx[i];
        int newY = curY + dy[i];

        if(newX < 0 || newX >= 5 || newY < 0 || newY >= 5){
            continue;
        }

        dfs(newX, newY, num * 10 + board[newX][newY], depth + 1);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 5; i++){
        for(int j = 0; j < 5; j++){
            cin >> board[i][j];
        }
    }

    for(int i = 0; i < 5; i++){
        for(int j = 0; j < 5; j++){
            dfs(i, j, board[i][j], 0);
        }
    }

    cout << ans.size() << "\n";

    return 0;
}****
```