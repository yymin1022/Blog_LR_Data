[문제 바로가기](https://boj.kr/2583)

```c++
#include <bits/stdc++.h>

using namespace std;

void bfs();

int M, N, K;
int area[101][101];

queue<pair<int, int>> bfsQ;
vector<int> ans;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> M >> N >> K;

    for(int i = 0; i < K; i++){
        int x1, x2, y1, y2;
        cin >> x1 >> y1 >> x2 >> y2;

        for(int j = x1; j < x2; j++){
            for(int k = y1; k < y2; k++){
                area[k][j] = 1;
            }
        }
    }

    int cnt = 0;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            if(!area[i][j]){
                bfsQ.push(make_pair(i, j));
                bfs();
                cnt++;
            }
        }
    }

    cout << cnt << "\n";

    sort(ans.begin(), ans.end());
    for(int i = 0; i < cnt; i++){
        cout << ans[i] << " ";
    }

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

            if(newX < 0 || newX >= M || newY < 0 || newY >= N){
                continue;
            }

            if(!area[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                area[newX][newY] = 1;
            }
        }
    }

    if(cnt > 1)cnt--;

    ans.push_back(cnt);
}```