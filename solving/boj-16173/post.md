[문제 바로가기](https://boj.kr/16173)

```c++
#include <bits/stdc++.h>

using namespace std;

int board[5][5];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> board[i][j];
        }
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(0, 0));
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(board[curX][curY] == -1){
            cout << "HaruHaru" << "\n";
            return 0;
        }else if(board[curX][curY] == 0){
            continue;
        }

        if(curX + board[curX][curY] < N){
            bfsQ.push(make_pair(curX + board[curX][curY], curY));
        }
        if(curY + board[curX][curY] < N){
            bfsQ.push(make_pair(curX, curY + board[curX][curY]));
        }
    }

    cout << "Hing" << "\n";

    return 0;
}
```