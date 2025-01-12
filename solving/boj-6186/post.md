[문제 바로가기](https://boj.kr/6186)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];
char grass[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C;
    cin >> R >> C;

    for(int i = 0; i < R; i++){
        string input;
        cin >> input;

        for(int j = 0; j < C; j++){
            grass[i][j] = input[j];
        }
    }

    int ans = 0;
    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            if(grass[i][j] == '#' && !isVisit[i][j]) {
                ans++;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    int dx[4] = {0, 1, 0, -1};
                    int dy[4] = {1, 0, -1, 0};
                    for(int k = 0; k < 4; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                            continue;
                        }

                        if(!isVisit[newX][newY] && grass[newX][newY] == '#'){
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