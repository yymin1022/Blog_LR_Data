[문제 바로가기](https://boj.kr/1600)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[201][201][31];
int monkey[201][201];

typedef struct{
    int hCnt;
    int mvCnt;
    int x;
    int y;
} moving;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int K, W, H;
    cin >> K >> W >> H;

    for(int i = 0; i < H; i++){
        for(int j = 0; j < W; j++){
            cin >> monkey[i][j];
        }
    }

    queue<moving> bfsQ;
    bfsQ.push({0, 0, 0, 0});
    isVisit[0][0][0] = false;

    while(!bfsQ.empty()){
        int curCnt = bfsQ.front().hCnt;
        int mvCnt = bfsQ.front().mvCnt;
        int curX = bfsQ.front().x;
        int curY = bfsQ.front().y;
        bfsQ.pop();

        if(curX == H - 1 && curY == W - 1){
            cout << mvCnt << "\n";
            return 0;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= H || newY < 0 || newY >= W){
                continue;
            }

            if(!isVisit[newX][newY][curCnt] && !monkey[newX][newY]){
                bfsQ.push({curCnt, mvCnt + 1, newX, newY});
                isVisit[newX][newY][curCnt] = true;
            }
        }

        if(curCnt < K){
            int dxN[8] = {-1, 1, 2, 2, 1, -1, -2, -2};
            int dyN[8] = {2, 2, 1, -1, -2, -2, -1, 1};
            for(int i = 0; i < 8; i++){
                int newX = curX + dxN[i];
                int newY = curY + dyN[i];

                if(newX < 0 || newX >= H || newY < 0 || newY >= W){
                    continue;
                }

                if(!isVisit[newX][newY][curCnt + 1] && !monkey[newX][newY]){
                    bfsQ.push({curCnt + 1, mvCnt + 1, newX, newY});
                    isVisit[newX][newY][curCnt + 1] = true;
                }
            }
        }
    }
    
    cout << -1 << "\n";
    
    return 0;
}
```