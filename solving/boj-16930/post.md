[문제 바로가기](https://boj.kr/16930)

```c++
#include <bits/stdc++.h>

using namespace std;

char arr[1001][1001];
int isVisit[1001][1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= M; j++){
            cin >> arr[i][j];
            isVisit[i][j] = 987654321;
        }
    }

    int x1, x2, y1, y2;
    cin >> x1 >> y1 >> x2 >> y2;

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(x1, y1));
    isVisit[x1][y1] = 0;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            for(int j = 1; j <= K; j++){
                int newX = curX + dx[i] * j;
                int newY = curY + dy[i] * j;

                if(newX < 1 || newX > N || newY < 1 || newY > M || arr[newX][newY] == '#' || isVisit[newX][newY] < isVisit[curX][curY] + 1){
                    break;
                }

                if(isVisit[newX][newY] == 987654321){
                    bfsQ.push(make_pair(newX, newY));
                    isVisit[newX][newY] = isVisit[curX][curY] + 1;
                }
            }
        }
    }

    if(isVisit[x2][y2] == 987654321){
        cout << -1 << "\n";
    }else{
        cout << isVisit[x2][y2] << "\n";
    }

    return 0;
}
```