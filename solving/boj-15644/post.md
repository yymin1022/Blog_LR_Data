[문제 바로가기](https://boj.kr/15644)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool isVisit[11][11][11][11];
char maze[11][11];
char direction[5] = "RDLU";
int N, M;
int blueX, blueY, redX, redY;
struct marble{
    int blueX;
    int blueY;
    int redX;
    int redY;
    int moveCnt;
};

marble moved[11][11][11][11];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            maze[i][j] = input[j];
            if(maze[i][j] == 'B'){
                blueX = i;
                blueY = j;
            }
            if(maze[i][j] == 'R'){
                redX = i;
                redY = j;
            }
        }
    }

    queue<marble> bfsQ;
    bfsQ.push({blueX, blueY, redX, redY, 0});
    isVisit[blueX][blueY][redX][redY] = true;

    while(!bfsQ.empty()){
        marble cur = bfsQ.front();
        bfsQ.pop();

        if(maze[cur.redX][cur.redY] == 'O'){
            string path;
            marble &tmp = moved[cur.blueX][cur.blueY][cur.redX][cur.redY];
            while (tmp.redX != 0) {
                int newRedX = tmp.redX;
                int newRedY = tmp.redY;
                int newBlueX = tmp.blueX;
                int newBlueY = tmp.blueY;

                path.push_back(direction[tmp.moveCnt]);
                tmp = moved[newBlueX][newBlueY][newRedX][newRedY];
            }
            reverse(path.begin(), path.end());

            cout << cur.moveCnt << "\n";
            cout << path << "\n";

            return 0;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newBlueX = cur.blueX;
            int newBlueY = cur.blueY;
            int newRedX = cur.redX;
            int newRedY = cur.redY;

            int blueCnt = 0;
            while(maze[newBlueX + dx[i]][newBlueY + dy[i]] != '#' && maze[newBlueX][newBlueY] != 'O'){
                newBlueX += dx[i];
                newBlueY += dy[i];
                blueCnt++;
            }

            int redCnt = 0;
            while(maze[newRedX + dx[i]][newRedY + dy[i]] != '#' && maze[newRedX][newRedY] != 'O'){
                newRedX += dx[i];
                newRedY += dy[i];
                redCnt++;
            }

            if(maze[newBlueX][newBlueY] == 'O'){
                continue;
            }

            if(newBlueX == newRedX && newBlueY == newRedY){
                if(blueCnt > redCnt){
                    newBlueX -= dx[i];
                    newBlueY -= dy[i];
                }else{
                    newRedX -= dx[i];
                    newRedY -= dy[i];
                }
            }

            if(isVisit[newBlueX][newBlueY][newRedX][newRedY]){
                continue;
            }

            if(cur.moveCnt < 10){
                isVisit[newBlueX][newBlueY][newRedX][newRedY] = true;
                bfsQ.push({newBlueX, newBlueY, newRedX, newRedY, cur.moveCnt + 1});
                moved[newBlueX][newBlueY][newRedX][newRedY] = {cur.blueX, cur.blueY, cur.redX, cur.redY, i};
            }
        }
    }

    cout << "-1" << "\n";

    return 0;
}
```