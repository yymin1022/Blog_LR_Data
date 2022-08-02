[문제 바로가기](https://boj.kr/7562)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

int board[301][301];
int L, N, fromX, fromY, toX, toY;

int dx[8] = {-2, -1, 1, 2, 2, 1, -1, -2};
int dy[8] = {1, 2, 2, 1, -1, -2, -2, -1};

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        memset(board, 0, sizeof(board));

        cin >> L >> fromX >> fromY >> toX >> toY;
        bfs();
    }

    return 0;
}

void bfs(){
    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(fromX, fromY));
    
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();
        
        if(curX == toX && curY == toY){
            cout << board[curX][curY] << "\n";
            break;
        }

        for(int i = 0; i < 8; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= L || newY < 0 || newY >= L){
                continue;
            }

            if(!board[newX][newY]){
                board[newX][newY] = board[curX][curY] + 1;
                bfsQ.push(make_pair(newX, newY));
            }
        }
    }
}```