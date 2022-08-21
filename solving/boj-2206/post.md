[문제 바로가기](https://boj.kr/2206)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[1001][1001];
int dist[1001][1001][2];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 1; i <= N; i++){
        string input;
        cin >> input;
        for(int j = 1; j <= M; j++){
            board[i][j] = input[j - 1] - '0';
        }
    }

    queue<pair<pair<int, int>, int>> bfsQ;
    bfsQ.push(make_pair(make_pair(1, 1), 0));
    dist[1][1][0] = 1;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first.first;
        int curY = bfsQ.front().first.second;
        int curBroken = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX > 0 && newX <= N && newY > 0 && newY <= M){
                if(board[newX][newY] && !curBroken && !dist[newX][newY][1]){
                    bfsQ.push(make_pair(make_pair(newX, newY), 1));
                    dist[newX][newY][1] = dist[curX][curY][curBroken] + 1;
                }else if(!board[newX][newY] && !dist[newX][newY][curBroken]){
                    bfsQ.push(make_pair(make_pair(newX, newY), curBroken));
                    dist[newX][newY][curBroken] = dist[curX][curY][curBroken] + 1;
                }
            }
        }
    }

    int ans = -1;
    if(dist[N][M][0] && dist[N][M][1]){
        ans = min(dist[N][M][0], dist[N][M][1]);
    }else if(dist[N][M][0]){
        ans = dist[N][M][0];
    }else if(dist[N][M][1]){
        ans = dist[N][M][1];
    }

    cout << ans << "\n";

    return 0;
}
```