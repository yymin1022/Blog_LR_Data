[문제 바로가기](https://boj.kr/21938)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[1001][1001];
int arr[1001][1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, T;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            int A, B, C;
            cin >> A >> B >> C;
            arr[i][j] = (A + B + C) / 3;
        }
    }

    cin >> T;

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(arr[i][j] >= T && !isVisit[i][j]){
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

                        if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                            continue;
                        }

                        if(arr[newX][newY] >= T && !isVisit[newX][newY]) {
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