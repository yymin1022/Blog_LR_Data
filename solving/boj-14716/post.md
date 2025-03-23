[문제 바로가기](https://boj.kr/14716)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[251][251];
int panel[251][251];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N;
    cin >> M >> N;

    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            cin >> panel[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            if(panel[i][j] == 1 && !isVisit[i][j]){
                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                ans++;
                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                    int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                    for(int k = 0; k < 8; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= M || newY < 0 || newY >= N){
                            continue;
                        }

                        if(panel[newX][newY] == 1 && !isVisit[newX][newY]){
                            bfsQ.push(make_pair(newX, newY));
                            isVisit[newX][newY] = true;
                        }
                    }
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```