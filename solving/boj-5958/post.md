[문제 바로가기](https://boj.kr/5958)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001][1001];
char space[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < N; j++){
            space[i][j] = input[j];
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(space[i][j] == '*' && !isVisit[i][j]){
                ans++;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    int dx[4] = {0, 1, 0, -1};
                    int dy[4] = {1, 0, -1, 0};
                    for(int k = 0; k < 4; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                            continue;
                        }

                        if(space[newX][newY] == '*' && !isVisit[newX][newY]){
                            bfsQ.push(make_pair(newX, newY));
                            isVisit[newX][newY] = true;
                        }
                    }
                }
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```
