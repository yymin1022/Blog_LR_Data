[문제 바로가기](https://boj.kr/17086)

```c++
#include <bits/stdc++.h>

using namespace std;

int cntVisit[51][51];
int ocean[51][51];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> ocean[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(ocean[i][j] == 0){
                memset(cntVisit, 0, sizeof(cntVisit));

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                cntVisit[i][j] = 1;

                int cnt = 987654321;
                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    if(ocean[curX][curY] == 1){
                        cnt = min(cntVisit[curX][curY], cnt);
                    }

                    int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                    int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                    for(int k = 0; k < 8; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                            continue;
                        }

                        if(cntVisit[newX][newY] == 0){
                            bfsQ.push(make_pair(newX, newY));
                            cntVisit[newX][newY] = cntVisit[curX][curY] + 1;
                        }
                    }
                }

                ans = max(cnt, ans);
            }
        }
    }

    cout << ans - 1 << "\n";

    return 0;
}
```