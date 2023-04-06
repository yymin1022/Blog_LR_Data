[문제 바로가기](https://boj.kr/1743)

```c++
#include <bits/stdc++.h>

using namespace std;

bool arr[101][101];
bool isVisit[101][101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    vector<pair<int, int>> food;
    for(int i = 0; i < K; i++){
        int r, c;
        cin >> r >> c;
        arr[r - 1][c - 1] = true;
        food.push_back(make_pair(r - 1, c - 1));
    }

    int ans = 0;
    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < K; i++){
        if(isVisit[food[i].first][food[i].second]){
            continue;
        }

        int cnt = 0;
        bfsQ.push(food[i]);
        isVisit[food[i].first][food[i].second] = true;

        while(!bfsQ.empty()){
            int curX = bfsQ.front().first;
            int curY = bfsQ.front().second;
            bfsQ.pop();
            cnt++;
            
            int dx[4] = {0, 1, 0, -1};
            int dy[4] = {1, 0, -1, 0};
            for(int j = 0; j < 4; j++){
                int newX = curX + dx[j];
                int newY = curY + dy[j];

                if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                    continue;
                }

                if(!isVisit[newX][newY] && arr[newX][newY]){
                    bfsQ.push(make_pair(newX, newY));
                    isVisit[newX][newY] = true;
                }
            }
        }
        ans = max(cnt, ans);
    }

    cout << ans << "\n";
    
    return 0;
}
```