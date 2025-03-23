[문제 바로가기](https://boj.kr/6080)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001][1001];
int arr[1001][1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

	int R, C;
    cin >> R >> C;

    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            cin >> arr[i][j];
        }
    }

    int ans = 0;
    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            if(arr[i][j] > 0 && !isVisit[i][j]){
                ans++;

                queue<pair<int, int>> bfsQ;
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;

                while(!bfsQ.empty()){
                    int curX = bfsQ.front().first;
                    int curY = bfsQ.front().second;
                    bfsQ.pop();

                    int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                    int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                    for(int k = 0; k < 8; k++){
                        int newX = curX + dx[k];
                        int newY = curY + dy[k];

                        if(newX < 0 || newX >= R || newY < 0 || newY >= C){
                            continue;
                        }

                        if(!isVisit[newX][newY] && arr[newX][newY] > 0){
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
