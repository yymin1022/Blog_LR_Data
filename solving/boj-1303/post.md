[문제 바로가기](https://boj.kr/1303)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[101][101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<string> war(M);
    for(int i = 0; i < M; i++){
        cin >> war[i];
    }

    int blue = 0;
    int white = 0;
    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < M; i++){
        for(int j = 0; j < N; j++){
            if(!isVisit[i][j]){
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                int temp = 0;
                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();
                    temp++;

                    int dx[4] = {0, 1, 0, -1};
                    int dy[4] = {1, 0, -1, 0};
                    for(int k = 0; k < 4; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= M || newY < 0 || newY >= N){
                            continue;
                        }

                        if(war[newX][newY] == war[i][j] && !isVisit[newX][newY]){
                            bfsQ.push(make_pair(newX, newY));
                            isVisit[newX][newY] = true;
                        }
                    }
                }

                if(war[i][j] == 'W'){
                    white += temp * temp;
                }else{
                    blue += temp * temp;
                }
            }
        }
    }

    cout << white << " ";
    cout << blue << "\n";

    return 0;
}
```