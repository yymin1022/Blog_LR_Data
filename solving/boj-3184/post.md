[문제 바로가기](https://boj.kr/3184)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[251][251];
char farm[251][251];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    int ans[2] = {0, 0};
    vector<pair<int, int>> lambs;
    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            cin >> farm[i][j];

            if(farm[i][j] == 'o'){
                ans[0]++;
                lambs.push_back(make_pair(i, j));
            }else if(farm[i][j] == 'v'){
                ans[1]++;
            }
        }
    }

    for(int l = 0; l < lambs.size(); l++){
        if(!isVisit[lambs[l].first][lambs[l].second]){
            queue<pair<int, int>> bfsQ;
            bfsQ.push(lambs[l]);

            int cnt[2] = {0, 0};
            while(!bfsQ.empty()){
                int curX = bfsQ.front().first;
                int curY = bfsQ.front().second;
                bfsQ.pop();

                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int i = 0; i < 4; i++){
                    int newX = curX + dx[i];
                    int newY = curY + dy[i];

                    if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                        continue;
                    }

                    if(!isVisit[newX][newY] && farm[newX][newY] != '#'){
                        bfsQ.push(make_pair(newX, newY));
                        isVisit[newX][newY] = true;

                        if(farm[newX][newY] == 'o'){
                            cnt[0]++;
                        }else if(farm[newX][newY] == 'v'){
                            cnt[1]++;
                        }
                    }
                }
            }

            if(cnt[0] > cnt[1]){
                ans[1] -= cnt[1];
            }else{
                ans[0] -= cnt[0];
            }
        }
    }

    cout << ans[0] << " ";
    cout << ans[1] << "\n";

    return 0;
}
```
