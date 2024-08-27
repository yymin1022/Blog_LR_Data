[문제 바로가기](https://boj.kr/18405)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[201][201];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<pair<int, pair<int, int>>> virus;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> board[i][j];

            if(board[i][j] > 0){
                virus.push_back(make_pair(board[i][j], make_pair(i, j)));
            }
        }
    }

    int S, X, Y;
    cin >> S >> X >> Y;

    sort(virus.begin(), virus.end());

    while(S--){
        int virusCnt = virus.size();
        for(int v = 0; v < virusCnt; v++){
            int curV = virus[v].first;
            int curX = virus[v].second.first;
            int curY = virus[v].second.second;

            int dx[4] = {0, 1, 0, -1};
            int dy[4] = {1, 0, -1, 0};
            for(int i = 0; i < 4; i++){
                int newX = curX + dx[i];
                int newY = curY + dy[i];

                if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                    continue;
                }

                if(board[newX][newY] == 0){
                    board[newX][newY] = curV;
                    virus.push_back(make_pair(curV, make_pair(newX, newY)));
                }
            }
        }

        if(board[X - 1][Y - 1]){
            break;
        }
    }

    cout << board[X - 1][Y - 1] << "\n";

    return 0;
}
```