[문제 바로가기](https://boj.kr/13565)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001][1001];
int board[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < M; j++){
            board[i][j] = input[j] - '0';
        }
    }

    for(int i = 0; i < M; i++){
        if(board[0][i] == 0){
            queue<pair<int, int>> bfsQ;
            bfsQ.push(make_pair(0, i));
            isVisit[0][i] = true;

            while(!bfsQ.empty()){
                int curX = bfsQ.front().first;
                int curY = bfsQ.front().second;
                bfsQ.pop();

                if(curX == N - 1){
                    cout << "YES" << "\n";
                    return 0;
                }

                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int k = 0; k < 4; k++){
                    int newX = curX + dx[k];
                    int newY = curY + dy[k];

                    if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                        continue;
                    }

                    if(board[newX][newY] == 0 && !isVisit[newX][newY]){
                        bfsQ.push(make_pair(newX, newY));
                        isVisit[newX][newY] = true;
                    }
                }
            }
        }
    }

    cout << "NO" << "\n";

    return 0;
}
```