[문제 바로가기](https://boj.kr/1261)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[101][101];
int dist[101][101];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        for(int j = 0; j < N; j++){
            board[i][j] = input[j] - '0';
            dist[i][j] = 987654321;
        }
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(0, 0));
    dist[0][0] = 0;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= M || newY < 0 || newY >= N){
                continue;
            }

            if(board[newX][newY] == 0){
                if(dist[newX][newY] > dist[curX][curY]){
                    dist[newX][newY] = dist[curX][curY];
                    bfsQ.push(make_pair(newX, newY));
                }
            }else{
                if(dist[newX][newY] > dist[curX][curY] + 1){
                    dist[newX][newY] = dist[curX][curY] + 1;
                    bfsQ.push(make_pair(newX, newY));
                }
            }
        }
    }

    cout << dist[M - 1][N - 1] << "\n";

    return 0;
}
```