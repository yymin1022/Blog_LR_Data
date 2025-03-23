[문제 바로가기](https://boj.kr/6593)

```c++
#include  <bits/stdc++.h>

using namespace std;

char building[31][31][31];
int visitTime[31][31][31];

typedef struct node{
    int x;
    int y;
    int z;
} node;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int L, R, C;
        cin >> L >> R >> C;

        if(L == 0 && R == 0 && C == 0){
            break;
        }

        node from, to;
        for(int i = 0; i < L; i++){
            for(int j = 0; j < R; j++){
                string input;
                cin >> input;

                for(int k = 0; k < C; k++){
                    building[i][j][k] = input[k];
                    visitTime[i][j][k] = 0;

                    if(building[i][j][k] == 'S'){
                        from = {i, j, k};
                        visitTime[i][j][k] = 1;
                    }else if(building[i][j][k] == 'E'){
                        to = {i, j, k};
                    }
                }
            }
        }

        queue<node> bfsQ;
        bfsQ.push(from);

        bool isEscaped = false;
        while(!bfsQ.empty()){
            int curX = bfsQ.front().x;
            int curY = bfsQ.front().y;
            int curZ = bfsQ.front().z;
            bfsQ.pop();

            if(building[curX][curY][curZ] == 'E'){
                isEscaped = true;
                break;
            }

            int dx[6] = {0, 0, 0, 0, 1, -1};
            int dy[6] = {1, 0, -1, 0, 0, 0};
            int dz[6] = {0, 1, 0, -1, 0, 0};
            for(int i = 0; i < 6; i++){
                int newX = curX + dx[i];
                int newY = curY + dy[i];
                int newZ = curZ + dz[i];

                if(newX < 0 || newX >= L || newY < 0 || newY >= R || newZ < 0 || newZ >= C){
                    continue;
                }

                if(visitTime[newX][newY][newZ] == 0 && building[newX][newY][newZ] != '#'){
                    bfsQ.push({newX, newY, newZ});
                    visitTime[newX][newY][newZ] = visitTime[curX][curY][curZ] + 1;
                }
            }
        }

        if(isEscaped){
            cout << "Escaped in "<< visitTime[to.x][to.y][to.z] - 1 << " minute(s)." << "\n";
        }else{
            cout << "Trapped!" << "\n";
        }
    }

    return 0;
}
```