[문제 바로가기](https://boj.kr/17198)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[11][11];
char farm[11][11];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < 10; i++){
        for(int j = 0; j < 10; j++){
            cin >> farm[i][j];

            if(farm[i][j] == 'L'){
                bfsQ.push(make_pair(i, j));
                cnt[i][j] = 1;
            }
        }
    }

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= 10 || newY < 0 || newY >= 10 || cnt[newX][newY] != 0){
                continue;
            }

            if(farm[newX][newY] == 'B'){
                cout << cnt[curX][curY] - 1 << "\n";
                return 0;
            }

            if(farm[newX][newY] == '.'){
                bfsQ.push(make_pair(newX, newY));
                cnt[newX][newY] = cnt[curX][curY] + 1;
            }
        }
    }

    return 0;
}
```
