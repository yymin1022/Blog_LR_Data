[문제 바로가기](https://boj.kr/31575)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[301][301];
int board[301][301];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> M >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> board[i][j];
        }
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(0, 0));
    isVisit[0][0] = true;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1};
        int dy[4] = {1, 0};
        for(int i = 0; i < 2; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(!isVisit[newX][newY] && board[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                isVisit[newX][newY] = true;
            }
        }
    }

    cout << (isVisit[N - 1][M - 1] ? "Yes" : "No") << "\n";

    return 0;
}
```
