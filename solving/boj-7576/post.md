[문제 바로가기](https://boj.kr/7576)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int M, N;
    cin >> N >> M;

    int days[1001][1001];
    int tomato[1001][1001];
    queue<pair<int, int>> bfs;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            cin >> tomato[i][j];
            days[i][j] = -1;

            if(tomato[i][j] == 1){
                bfs.push(make_pair(i, j));
                days[i][j] = 0;
            }
        }
    }

    while(!bfs.empty()){
        int curX = bfs.front().first;
        int curY = bfs.front().second;
        bfs.pop();
        
        int dx[] = {-1, 0, 1, 0};
        int dy[] = {0, -1, 0, 1};
        for(int i = 0; i < 4; i++){
            int tempX = curX + dx[i];
            int tempY = curY + dy[i];

            if(tempX < 0 || tempX >= M || tempY < 0 || tempY >= N){
                continue;
            }
            if(days[tempX][tempY] >= 0 || tomato[tempX][tempY] == -1){
                continue;
            }

            days[tempX][tempY] = days[curX][curY] + 1;
            bfs.push(make_pair(tempX, tempY));
        }
    }
    
    int answer = 0;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            if(days[i][j] == -1 && tomato[i][j] == 0){
                cout << -1 << "\n";
                return 0;
            }
            
            answer = max(answer, days[i][j]);
        }
    }

    cout << answer << "\n";

    return 0;
}
```