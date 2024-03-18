[문제 바로가기](https://boj.kr/11123)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];
char lamb[101][101];
int dx[4] = {0, 1, 0, -1};
int dy[4] = {1, 0, -1, 0};

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int H, W;
        cin >> H >> W;

        vector<pair<int, int>> lambList;
        for(int i = 0; i < H; i++){
            string input;
            cin >> input;

            for(int j = 0; j < W; j++){
                isVisit[i][j] = false;
                lamb[i][j] = input[j];

                if(lamb[i][j] == '#'){
                    lambList.push_back(make_pair(i, j));
                }
            }
        }

        int ans = 0;
        for(int i = 0; i < lambList.size(); i++){
            int curLambX = lambList[i].first;
            int curLambY = lambList[i].second;

            if(!isVisit[curLambX][curLambY]){
                ans++;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(lambList[i]);
                isVisit[curLambX][curLambY] = true;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    for(int j = 0; j < 4; j++){
                        int newX = curX + dx[j];
                        int newY = curY + dy[j];

                        if(newX < 0 || newX >= H || newY < 0 || newY >= W){
                            continue;
                        }

                        if(!isVisit[newX][newY] && lamb[newX][newY] == '#'){
                            bfsQ.push(make_pair(newX, newY));
                            isVisit[newX][newY] = true;
                        }
                    }
                }
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```
