[문제 바로가기](https://boj.kr/14442)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[1001][1001];
int visitCnt[1001][1001][11];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            board[i][j] = input[j] - '0';
        }
    }

    queue<pair<pair<int, int>, int>> bfsQ;
    bfsQ.push(make_pair(make_pair(0, 0), 0));
    visitCnt[0][0][0] = 1;

    while(!bfsQ.empty()){
        int curK = bfsQ.front().second;
        int curX = bfsQ.front().first.first;
        int curY = bfsQ.front().first.second;
        bfsQ.pop();

        if(curX == N - 1 && curY == M - 1){
            cout << visitCnt[N - 1][M - 1][curK] << "\n";
            return 0;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newK = curK;
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(visitCnt[newX][newY][newK] == 0 && board[newX][newY] == 0){
                bfsQ.push(make_pair(make_pair(newX, newY), newK));
                visitCnt[newX][newY][newK] = visitCnt[curX][curY][curK] + 1;
            }

            newK = curK + 1;
            if(curK < K && visitCnt[newX][newY][newK] == 0 && board[newX][newY] == 1){
                bfsQ.push(make_pair(make_pair(newX, newY), newK));
                visitCnt[newX][newY][newK] = visitCnt[curX][curY][curK] + 1;
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}
```