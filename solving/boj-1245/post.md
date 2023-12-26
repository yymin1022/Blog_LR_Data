[문제 바로가기](https://boj.kr/1245)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];
int mountain[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> mountain[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(!isVisit[i][j]){
                bool flag = true;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                    int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                    for(int k = 0; k < 8; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= N || newY < 0 ||  newY >= M){
                            continue;
                        }

                        if(mountain[newX][newY] > mountain[curX][curY]){
                            flag = false;
                        }

                        if(!isVisit[newX][newY] && mountain[newX][newY] == mountain[curX][curY]){
                            bfsQ.push(make_pair(newX, newY));
                            isVisit[newX][newY] = true;
                        }
                    }
                }
                if(flag){
                    ans++;
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```