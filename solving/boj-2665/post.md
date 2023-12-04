[문제 바로가기](https://boj.kr/2665)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[51][51];
int dist[51][51];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        for(int j = 0; j < N; j++){
            arr[i][j] = S[j] - '0';
            dist[i][j] = 987654321;
        }
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(0, 0));
    dist[0][0] = 0;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                continue;
            }

            int curD = dist[curX][curY] + (arr[curX][curY] ? 0 : 1);
            if(dist[newX][newY] > curD){
                dist[newX][newY] = curD;
                bfsQ.push(make_pair(newX, newY));
            }
        }
    }

    cout << dist[N - 1][N - 1] << "\n";

    return 0;
}
```