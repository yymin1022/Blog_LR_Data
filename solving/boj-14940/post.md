[문제 바로가기](https://boj.kr/14940)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001][1001];
int board[1001][1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> board[i][j];

            if(board[i][j] == 2){
                bfsQ.push(make_pair(i, j));
                board[i][j] = 0;
                isVisit[i][j] = true;
            }
        }
    }

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(!isVisit[newX][newY] && board[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                board[newX][newY] = board[curX][curY] + 1;
                isVisit[newX][newY] = true;
            }
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cout << (isVisit[i][j] || (!isVisit[i][j] && !board[i][j]) ? board[i][j] : -1) << " ";
        }
        cout << "\n";
    }

    return 0;
}
```