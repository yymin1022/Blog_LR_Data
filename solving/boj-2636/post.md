[문제 바로가기](https://boj.kr/2636)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];
int cheese[101][101];
int cheeseCnt;
int lastCnt;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> cheese[i][j];

            if(cheese[i][j]){
                cheeseCnt++;
                lastCnt++;
            }
        }
    }

    int cnt = 0;
    while(cheeseCnt){
        memset(isVisit, false, sizeof(isVisit));

        cnt++;
        lastCnt = cheeseCnt;
        queue<pair<int, int>> bfsQ;
        bfsQ.push(make_pair(0, 0));
        isVisit[0][0] = true;

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

                if(!cheese[newX][newY] && !isVisit[newX][newY]){
                    bfsQ.push(make_pair(newX, newY));
                }

                if(cheese[newX][newY] && !isVisit[newX][newY]){
                    cheese[newX][newY]--;
                    cheeseCnt--;
                }
                isVisit[newX][newY] = true;
            }
        }
    }

    cout << cnt << "\n";
    cout << lastCnt << "\n";

    return 0;
}

```