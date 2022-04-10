[문제 바로가기](https://boj.kr/7569)

```c++
#include <bits/stdc++.h>

using namespace std;

struct tomatoXYZ{
    int x, y, z;
};

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int H, M, N;
    cin >> N >> M >> H;

    int days[101][101][101];
    int tomato[101][101][101];
    queue<tomatoXYZ> bfs;
    for(int i = 0; i < H; i++){
        for(int j = 0; j < M; j++){
            for(int k = 0; k < N; k++){
                cin >> tomato[j][k][i];
                days[j][k][i] = -1;

                if(tomato[j][k][i] == 1){
                    bfs.push({j, k, i});
                    days[j][k][i] = 0;
                }
            }
        }
    }

    while(!bfs.empty()){
        int curX = bfs.front().x;
        int curY = bfs.front().y;
        int curZ = bfs.front().z;
        bfs.pop();
        
        int dx[] = { -1,0,1,0,0,0 };
        int dy[] = { 0,1,0,-1,0,0 };
        int dz[] = { 0,0,0,0,1,-1 };
        for(int i = 0; i < 6; i++){
            int tempX = curX + dx[i];
            int tempY = curY + dy[i];
            int tempZ = curZ + dz[i];

            if(tempX < 0 || tempX >= M || tempY < 0 || tempY >= N || tempZ < 0 || tempZ >= H){
                continue;
            }
            if(days[tempX][tempY][tempZ] >= 0 || tomato[tempX][tempY][tempZ] == -1){
                continue;
            }

            days[tempX][tempY][tempZ] = days[curX][curY][curZ] + 1;
            bfs.push({tempX, tempY, tempZ});
        }
    }
    
    int answer = 0;
    for(int i = 0; i < H; i++){
        for(int j = 0; j < M; j++){
            for(int k = 0; k < N; k++){
                if(days[j][k][i] == -1 && tomato[j][k][i] == 0){
                    cout << -1 << "\n";
                    return 0;
                }
                
                answer = max(answer, days[j][k][i]);
            }
        }
    }

    cout << answer << "\n";

    return 0;
}
```