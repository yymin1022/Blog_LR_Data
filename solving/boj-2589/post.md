[문제 바로가기](https://boj.kr/2589)

```c++
#include  <bits/stdc++.h>

using namespace std;

char island[51][51];
int visitCnt[51][51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> island[i][j];
        }
    }

    int ans = 0;
    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            memset(visitCnt, false, sizeof(visitCnt));

            if(island[i][j] == 'L' && !visitCnt[i][j]){
                bfsQ.push(make_pair(i, j));
                visitCnt[i][j] = 1;
            }

            while(!bfsQ.empty()){
                int curX = bfsQ.front().first;
                int curY = bfsQ.front().second;
                bfsQ.pop();

                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int k = 0; k < 4; k++){
                    int newX = curX + dx[k];
                    int newY = curY + dy[k];

                    if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                        continue;
                    }

                    if(island[newX][newY] == 'L' && !visitCnt[newX][newY]){
                        bfsQ.push(make_pair(newX, newY));
                        visitCnt[newX][newY] = visitCnt[curX][curY] + 1;
                        ans = max(visitCnt[newX][newY], ans);
                    }
                }
            }
        }
    }

    cout << ans - 1 << "\n";

    return 0;
}
```