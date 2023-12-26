[문제 바로가기](https://boj.kr/18404)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[501][501];
int cnt[501][501];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, X, Y;
    cin >> N >> M >> X >> Y;

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(X, Y));
    cnt[X][Y] = 0;
    isVisit[X][Y] = true;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[8] = {1, 2, 2, 1, -1, -2, -2, -1};
        int dy[8] = {2, 1, -1, -2, -2, -1, 1, 2};
        for(int i = 0; i < 8; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX <= 0 || newX > N || newY <= 0 || newY > N){
                continue;
            }

            if(!isVisit[newX][newY]){
                bfsQ.push(make_pair(newX, newY));
                cnt[newX][newY] = cnt[curX][curY] + 1;
                isVisit[newX][newY] = true;
            }
        }
    }

    while(M--){
        int A, B;
        cin >> A >> B;
        cout << cnt[A][B] << " ";
    }

    return 0;
}
```