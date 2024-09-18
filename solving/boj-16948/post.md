[문제 바로가기](https://boj.kr/16948)

```c++
#include <bits/stdc++.h>

using namespace std;

int cntVisit[201][201];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, R1, C1, R2, C2;
    cin >> N >> R1 >> C1 >> R2 >> C2;

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(R1, C1));
    cntVisit[R1][C1] = 1;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(curX == R2 && curY == C2){
            cout << cntVisit[curX][curY] -1 << "\n";
            return 0;
        }

        int dx[6] = {-2, -2, 0, 0, 2, 2};
        int dy[6] = {-1,  1, -2, 2, -1, 1};
        for(int i = 0; i < 6; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                continue;
            }

            if(cntVisit[newX][newY] == 0){
                bfsQ.push(make_pair(newX, newY));
                cntVisit[newX][newY] = cntVisit[curX][curY] + 1;
            }
        }
    }

    cout << -1 << "\n";

    return 0;
}
```