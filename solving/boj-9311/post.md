[문제 바로가기](https://boj.kr/9311)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int R, C;
        cin >> R >> C;

        char maze[16][16];
        int cntVisit[16][16];
        queue<pair<int, int>> bfsQ;
        for(int i = 0; i < R; i++){
            for(int j = 0; j < C; j++){
                char input;
                cin >> input;
                cntVisit[i][j] = 0;
                maze[i][j] = input;

                if(maze[i][j] == 'S'){
                    bfsQ.push(make_pair(i, j));
                    cntVisit[i][j] = 1;
                }
            }
        }

        bool isExit = false;
        while(!bfsQ.empty()){
            int curX = bfsQ.front().first;
            int curY = bfsQ.front().second;
            bfsQ.pop();

            if(maze[curX][curY] == 'G'){
                cout << "Shortest Path: " << cntVisit[curX][curY] - 1 << "\n";
                isExit = true;
                break;
            }

            int dx[4] = {0, 1, 0, -1};
            int dy[4] = {1, 0, -1, 0};
            for(int i = 0; i < 4; i++){
                int newX = curX + dx[i];
                int newY = curY + dy[i];

                if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                    continue;
                }

                if(cntVisit[newX][newY] == 0 && maze[newX][newY] != 'X'){
                    bfsQ.push(make_pair(newX, newY));
                    cntVisit[newX][newY] = cntVisit[curX][curY] + 1;
                }
            }
        }

        if(!isExit){
            cout << "No Exit" << "\n";
        }
    }

    return 0;
}
```