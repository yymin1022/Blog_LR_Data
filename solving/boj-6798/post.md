[문제 바로가기](https://boj.kr/6798)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[9][9];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int fromX, fromY, toX, toY;
    cin >> fromX >> fromY >> toX >> toY;

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(fromX, fromY));
    cnt[fromX][fromY] = 1;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[8] = {1, 2, 2, 1, -1, -2, -2, -1};
        int dy[8] = {2, 1, -1, -2, -2, -1, 1, 2};
        for(int i = 0; i < 8; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX <= 0 || newX > 8 || newY <= 0 || newY > 8){
                continue;
            }

            if(cnt[newX][newY] == 0){
                bfsQ.push(make_pair(newX, newY));
                cnt[newX][newY] = cnt[curX][curY] + 1;
            }
        }
    }

    cout << cnt[toX][toY] - 1 << "\n";

    return 0;
}
```