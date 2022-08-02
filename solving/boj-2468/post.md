[문제 바로가기](https://boj.kr/2468)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

int N;
int city[101][101];
int temp[101][101];

queue<pair<int, int>> bfsQ;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    int maxH = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> city[i][j];
            maxH = max(city[i][j], maxH);
        }
    }

    int ans = 1;
    for(int i = 1; i <= maxH; i++){
        memset(temp, 0, sizeof(temp));
        for(int j = 0; j < N; j++){
            for(int k = 0; k < N; k++){
                if(city[j][k] > i){
                    temp[j][k] = city[j][k];
                }
            }
        }

        int cnt = 0;
        for(int j = 0; j < N; j++){
            for(int k = 0; k < N; k++){
                if(temp[j][k]){
                    bfsQ.push(make_pair(j, k));
                    bfs();
                    cnt++;
                }
            }
        }

        ans = max(cnt, ans);
    }

    cout << ans << "\n";

    return 0;
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

            if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                continue;
            }

            if(temp[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                temp[newX][newY] = 0;
            }
        }
    }
}```