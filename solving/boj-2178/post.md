[문제 바로가기](https://boj.kr/2178)

```c++
#include <bits/stdc++.h>
using namespace std;

void bfs();

int M, N;
int maze[101][101];
int cnt[101][101];

int main(){
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        string input;
        cin >> input;
        for(int j = 1; j <= M; j++){
            maze[i][j] = input[j - 1] - '0';
        }
    }

    bfs();

    return 0;
}

void bfs(){
    queue<pair<int, int>> bfsQ;
    bfsQ.push({1, 1});
    cnt[1][1] = 1;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(curX == N && curY == M){
            cout << cnt[N][M] << "\n";
            break;
        }

        int dx[] = {-1, 0, 1, 0};
        int dy[] = {0, 1, 0, -1};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX > 0 && newX <= N && newY > 0 && newY <= M){
                if(cnt[newX][newY] == 0 && maze[newX][newY] == 1){
                    cnt[newX][newY] = cnt[curX][curY] + 1;
                    bfsQ.push(make_pair(newX, newY));
                }
            }
        }
    }
}```