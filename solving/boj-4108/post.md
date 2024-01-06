[문제 바로가기](https://boj.kr/4108)

```c++
#include  <bits/stdc++.h>

using namespace std;

char board[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    while(R && C){
        for(int i = 0; i < R; i++){
            string input;
            cin >> input;
            for(int j = 0; j < C; j++){
                board[i][j] = input[j];
            }
        }

        for(int i = 0; i < R; i++){
            for(int j = 0; j < C; j++){
                if(board[i][j] == '.'){
                    int cnt = 0;
                    int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                    int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                    for(int k = 0; k < 8; k++){
                        if(i + dx[k] < 0 || i + dx[k] >= R || j + dy[k] < 0 || j + dy[k] >= C){
                            continue;
                        }
                        if(board[i + dx[k]][j + dy[k]] == '*'){
                            cnt++;
                        }
                    }
                    board[i][j] = cnt + '0';
                }
            }
        }

        for(int i = 0; i < R; i++){
            for(int j = 0; j < C; j++){
                cout << board[i][j];
            }
            cout << "\n";
        }

        cin >> R >> C;
    }

    return 0;
}
```