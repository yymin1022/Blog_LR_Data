[문제 바로가기](https://boj.kr/2146)

```c++
#include <bits/stdc++.h>

using namespace std;

int dist[101][101];
int island[101][101];
int visitCnt[101][101];
queue<pair<int, int>> islandQ[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> island[i][j];
        }
    }

    int islandCnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(island[i][j] != 0 && visitCnt[i][j] == 0){
                islandCnt++;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                visitCnt[i][j] = islandCnt;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    bool isBorder = false;
                    int dx[4] = {0, 1, 0, -1};
                    int dy[4] = {1, 0, -1, 0};
                    for(int k = 0; k < 4; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                            continue;
                        }

                        if(visitCnt[newX][newY] == 0){
                            if(island[newX][newY] == 0){
                                isBorder = true;
                                continue;
                            }

                            bfsQ.push(make_pair(newX, newY));
                            visitCnt[newX][newY] = islandCnt;
                        }
                    }

                    if(isBorder){
                        islandQ[islandCnt].push(make_pair(curX, curY));
                    }
                }
            }
        }
    }

    int ans = 201;
    for(int i = 1; i <= islandCnt; i++){
        queue<pair<int, int>> bfsQ = islandQ[i];
        while(!bfsQ.empty()){
            int curX = bfsQ.front().first;
            int curY = bfsQ.front().second;
            bfsQ.pop();

            int dx[4] = {0, 1, 0, -1};
            int dy[4] = {1, 0, -1, 0};
            for(int k = 0; k < 4; k++){
                int newX = curX + dx[k];
                int newY = curY + dy[k];

                if(newX < 0 || newX >= N || newY < 0 || newY >= N || visitCnt[newX][newY] == i){
                    continue;
                }

                if(island[newX][newY] == 0){
                    bfsQ.push(make_pair(newX, newY));
                    dist[newX][newY] = dist[curX][curY] + 1;
                    visitCnt[newX][newY] = i;
                }else{
                    ans = min(dist[curX][curY], ans);
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}

```