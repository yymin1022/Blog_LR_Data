[문제 바로가기](https://boj.kr/2573)

```c++
#include <bits/stdc++.h>

using namespace std;

int findLand();
void bfs();
void melt();

bool isVisit[301][301];
int ocean[301][301];
int N, M;
queue<pair<int, int>> bfsQ;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> ocean[i][j];
        }
    }

    int ans = 0;
    int cnt = findLand();
    while(cnt == 1){
        melt();
        cnt = findLand();
        ans++;
    }

    if(!cnt){
        ans = 0;
    }

    cout << ans << "\n";

    return 0;
}

int findLand(){
    memset(isVisit, false, sizeof(isVisit));

    int cnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(ocean[i][j] && !isVisit[i][j]){
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;
                bfs();
                cnt++;
            }
        }
    }

    return cnt;
}

void bfs(){
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

            if(ocean[newX][newY] && !isVisit[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                isVisit[newX][newY] = true;
            }
        }
    }
}

void melt(){
    int tmp[301][301];
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            tmp[i][j] = 0;
            if(ocean[i][j]){
                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int p = 0; p < 4; p++){
                    int newX = i + dx[p];
                    int newY = j + dy[p];

                    if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                        continue;
                    }

                    if(!ocean[newX][newY]){
                        tmp[i][j]++;
                    }
                }
            }
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            ocean[i][j] = max(ocean[i][j] - tmp[i][j], 0);
        }
    }
}
```