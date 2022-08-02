[문제 바로가기](https://boj.kr/1926)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

int N, M, ans;

bool isVisit[501][501];
int area[501][501];

queue<pair<int, int>> bfsQ;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> area[i][j];
        }
    }

    int cnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(!isVisit[i][j] && area[i][j]){
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;
                bfs();
                cnt++;
            }
        }
    }

    cout << cnt << "\n" << ans << "\n";

    return 0;
}

void bfs(){
    int cnt = 0;
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();
        cnt++;

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(area[newX][newY] && !isVisit[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                isVisit[newX][newY] = true;
            }
        }
    }

    ans = max(ans, cnt);
}```