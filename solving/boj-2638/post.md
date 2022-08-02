[문제 바로가기](https://boj.kr/2638)

```c++
#include <bits/stdc++.h>

using namespace std;

bool checkMelt();
void bfs();

bool isVisit[101][101];
int paper[101][101];
int N, M;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> paper[i][j];
        }
    }

    bfs();

    int cnt = 0;
    while(checkMelt()){
        cnt++;
        bfs();
    }

    cout << cnt << "\n";

    return 0;
}

bool checkMelt(){
    bool isMelt = false;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(paper[i][j] >= 3){
                paper[i][j] = 0;
                isMelt = true;
            }else if(paper[i][j] == 2){
                paper[i][j] = 1;
            }
        }
    }

    return isMelt;
}

void bfs(){
    memset(isVisit, false, sizeof(isVisit));
    queue<pair<int, int>> bfsQ;

    bfsQ.push(make_pair(0, 0));
    isVisit[0][0] = true;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {1, 0, -1, 0};
        int dy[4] = {0, 1, 0, -1};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX >= 0 && newX < N && newY >= 0 && newY < M){
                if(!isVisit[newX][newY]){
                    if(paper[newX][newY]){
                        paper[newX][newY]++;
                    }else{
                        bfsQ.push(make_pair(newX, newY));
                        isVisit[newX][newY] = true;
                    }
                }
            }
        }
    }
}```