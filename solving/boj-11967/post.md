[문제 바로가기](https://boj.kr/11967)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isMovable[101][101];
bool isLight[101][101];
bool isVisit[101][101];
vector<pair<int, int>> switchList[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int a, b, c, d;
        cin >> a >> b >> c >> d;
        switchList[a][b].push_back(make_pair(c, d));
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(1, 1));
    isMovable[1][1] = true;
    isLight[1][1] = true;
    isVisit[1][1] = true;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        for(int i = 0; i < switchList[curX][curY].size(); i++){
            int switchX = switchList[curX][curY][i].first;
            int switchY = switchList[curX][curY][i].second;

            isLight[switchX][switchY] = true;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 1 || newX > N || newY < 1 || newY > N){
                continue;
            }

            isMovable[newX][newY] = true;
        }

        for(int i = 1; i <= N; i++){
            for(int j = 1; j <= N; j++){
                if(!isMovable[i][j] || !isLight[i][j] || isVisit[i][j]){
                    continue;
                }

                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;
            }
        }
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            if(isLight[i][j]){
                ans++;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```