[문제 바로가기](https://boj.kr/14502)

```c++
#include <bits/stdc++.h>

using namespace std;

void addWall(int);
void bfs();

bool isVisit[10][10];
int lab[10][10];
int testLab[10][10];

int ans;
int N, M;
vector<pair<int, int>> virus;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> lab[i][j];
            if(lab[i][j] == 2){
                virus.push_back(make_pair(i, j));
            }
        }
    }

    addWall(0);

    cout << ans << "\n";

    return 0;
}

void addWall(int cnt){
    if(cnt == 3){
        bfs();
        return;
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(!lab[i][j]){
                lab[i][j] = 1;
                addWall(cnt + 1);
                lab[i][j] = 0;
            }
        }
    }
}

void bfs(){
    memset(isVisit, false, sizeof(isVisit));
    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < virus.size(); i++){
        bfsQ.push(virus[i]);
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            testLab[i][j] = lab[i][j];
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

            if(newX >= 0 && newX < N && newY >= 0 && newY < M){
                if(!isVisit[newX][newY] && !testLab[newX][newY]){
                    bfsQ.push(make_pair(newX, newY));
                    isVisit[newX][newY] = true;
                    testLab[newX][newY] = 2;
                }
            }
        }
    }

    int safeCnt = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(!testLab[i][j]){
                safeCnt++;
            }
        }
    }

    ans = max(safeCnt, ans);
}
```