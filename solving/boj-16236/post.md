[문제 바로가기](https://boj.kr/16236)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

bool isVisit[21][21];
int answer = 0;
int N, sharkEat, sharkX, sharkY;
int S = 2;
int dist[21][21];
int ocean[21][21];
queue<pair<int, int>> bfsQ;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> ocean[i][j];
            
            if(ocean[i][j] == 9){
                sharkX = i;
                sharkY = j;
            }
        }
    }

    bfs();

    cout << answer << "\n";
    
    return 0;
}

void bfs(){
    while(true){
        memset(dist, 0, sizeof(dist));
        memset(isVisit, false, sizeof(isVisit));

        bfsQ.push(make_pair(sharkX, sharkY));
        isVisit[sharkX][sharkY] = true;

        bool isTarget = false;
        int targetD = 987654321;
        int targetX = 0;
        int targetY = 0;

        while(!bfsQ.empty()){
            int curX = bfsQ.front().first;
            int curY = bfsQ.front().second;
            bfsQ.pop();

            int dx[] = {0, -1, 1, 0};
            int dy[] = {-1, 0, 0, 1};
            for(int i = 0; i < 4; i++){
                int newX = curX + dx[i];
                int newY = curY + dy[i];

                if(newX >= 0 && newX < N && newY >= 0 && newY < N){
                    if(!isVisit[newX][newY] && ocean[newX][newY] <= S){
                        isVisit[newX][newY] = true;
                        bfsQ.push(make_pair(newX, newY));
                        dist[newX][newY] = dist[curX][curY] + 1;

                        if(ocean[newX][newY] > 0 && ocean[newX][newY] < S){
                            if(dist[newX][newY] < targetD){
                                isTarget = true;
                                targetD = dist[newX][newY];
                                targetX = newX;
                                targetY = newY;
                            }else if(dist[newX][newY] == targetD){
                                if(newX < targetX){
                                    isTarget = true;
                                    targetD = dist[newX][newY];
                                    targetX = newX;
                                    targetY = newY;
                                }else if(newX == targetX && newY < targetY){
                                    isTarget = true;
                                    targetD = dist[newX][newY];
                                    targetX = newX;
                                    targetY = newY;
                                }
                            }
                        }
                    }
                }
            }
        }

        if(!isTarget){
            break;
        }

        answer += targetD;
        ocean[sharkX][sharkY] = 0;
        ocean[targetX][targetY] = 0;
        sharkEat++;
        sharkX = targetX;
        sharkY = targetY;

        if(sharkEat == S){
            S++;
            sharkEat = 0;
        }
    }
}
```