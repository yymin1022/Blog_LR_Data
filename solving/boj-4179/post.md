[문제 바로가기](https://boj.kr/4179)

```c++
#include <bits/stdc++.h>

using namespace std;

char board[1001][1001];
int isVisit[1001][1001];
int isVisitFire[1001][1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    queue<pair<int, int>> fireQ;
    queue<pair<int, int>> jihoonQ;
    for(int i = 0; i < R; i++){
        string input;
        cin >> input;
        for(int j = 0; j < C; j++){
            board[i][j] = input[j];
            isVisit[i][j] = -1;
            isVisitFire[i][j] = -1;

            if(board[i][j] == 'F'){
                fireQ.push(make_pair(i, j));
                isVisitFire[i][j] = 0;
            }else if(board[i][j] == 'J'){
                jihoonQ.push(make_pair(i, j));
                isVisit[i][j] = 0;
            }
        }
    }

    while(!fireQ.empty()){
        int curX = fireQ.front().first;
        int curY = fireQ.front().second;
        fireQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                continue;
            }

            if(isVisitFire[newX][newY] >= 0 || board[newX][newY] == '#'){
                continue;
            }

            fireQ.push(make_pair(newX, newY));
            isVisitFire[newX][newY] = isVisitFire[curX][curY] + 1;
        }
    }

    while(!jihoonQ.empty()){
        int curX = jihoonQ.front().first;
        int curY = jihoonQ.front().second;
        jihoonQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                cout << isVisit[curX][curY] + 1 << "\n";
                return 0;
            }

            if(isVisit[newX][newY] >= 0 || board[newX][newY] == '#'){
                continue;
            }

            if(isVisitFire[newX][newY] >= 0 && isVisitFire[newX][newY] <= isVisit[curX][curY] + 1){
                continue;
            }

            jihoonQ.push(make_pair(newX, newY));
            isVisit[newX][newY] = isVisit[curX][curY] + 1;
        }
    }

    cout << "IMPOSSIBLE" << "\n";

    return 0;
}
```