[문제 바로가기](https://boj.kr/2823)

```c++
#include <bits/stdc++.h>

using namespace std;

char board[11][11];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    for (int i = 0; i < R; i++) {
        for (int j = 0; j < C; j++) {
            cin >> board[i][j];
        }
    }

    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            if(board[i][j] == '.'){
                int cnt = 0;

                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int k = 0; k < 4; k++){
                    int newX = i + dy[k];
                    int newY = j + dx[k];

                    if(newX < 0 || newX >= R || newY < 0 || newY >=C){
                        continue;
                    }
                    if(board[newX][newY] == '.'){
                        cnt++;
                    }
                }
                
                if(cnt < 2){
                    cout << 1 << "\n";
                    return 0;
                }
            }
        }
    }

    cout << 0 << "\n";

    return 0;
}
```