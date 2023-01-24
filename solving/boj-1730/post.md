[문제 바로가기](https://boj.kr/1730)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[11][11];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    string cmd;
    cin >> cmd;

    int x = 0;
    int y = 0;
    for(int i = 0; i < cmd.size(); i++){
        if(cmd[i] == 'D' && x + 1 >= N){
            continue;
        }else if(cmd[i] == 'U' && x - 1 < 0){
            continue;
        }else if(cmd[i] == 'R' && y + 1 >= N){
            continue;
        }else if(cmd[i] == 'L' && y - 1 < 0){
            continue;
        }
        if(cmd[i] == 'D' || cmd[i] == 'U'){
            if(board[x][y] == 0){
                board[x][y] = 1;
            }else if(board[x][y] == 2) {
                board[x][y] = 3;
            }
        }else{
            if(board[x][y] == 0){
                board[x][y] = 2;
            }else if(board[x][y] == 1){
                board[x][y] = 3;
            }
        }
        if(cmd[i] == 'D' && x + 1 < N){
            x++;
        }else if(cmd[i] == 'U' && x - 1 >= 0){
            x--;
        }else if(cmd[i] == 'R' && y + 1 < N){
            y++;
        }else if(cmd[i] == 'L' && y - 1 >= 0){
            y--;
        }
        if(cmd[i] == 'D' || cmd[i] == 'U'){
            if(board[x][y] == 0){
                board[x][y] = 1;
            }else if(board[x][y] == 2) {
                board[x][y] = 3;
            }
        }else{
            if(board[x][y] == 0){
                board[x][y] = 2;
            }else if(board[x][y] == 1){
                board[x][y] = 3;
            }
        }
    }

    char arr[4] = {46, 124, 45, 43};
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cout << arr[board[i][j]];
        }
        cout << "\n";
    }

    return 0;
}
```