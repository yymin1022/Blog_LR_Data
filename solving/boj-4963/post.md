[문제 바로가기](https://boj.kr/4963)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

bool isVisit[51][51];
int W, H;
int ocean[51][51];

queue<pair<int, int>> bfsQ;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> W >> H;

    while(W && H){
        memset(isVisit, false, sizeof(isVisit));
        memset(ocean, 0, sizeof(ocean));

        for(int i = 0; i < H; i++){
            for(int j = 0; j < W; j++){
                cin >> ocean[i][j];
            }
        }

        int cnt = 0;
        for(int i = 0; i < H; i++){
            for(int j = 0; j < W; j++){
                if(ocean[i][j] && !isVisit[i][j]){
                    bfsQ.push(make_pair(i, j));
                    isVisit[i][j] = true;
                    bfs();
                    cnt++;
                }
            }
        }

        cout << cnt << "\n";

        cin >> W >> H;
    }

    return 0;
}

void bfs(){
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[8] = {-1, 0, 1, 1, 1, 0, -1, -1};
        int dy[8] = {1, 1, 1, 0, -1, -1, -1, 0};
        for(int i = 0; i < 8; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= H || newY < 0 || newY >= W){
                continue;
            }

            if(!isVisit[newX][newY] && ocean[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                isVisit[newX][newY] = true;
            }
        }
    }
}```