[문제 바로가기](https://boj.kr/16174)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[65][65];
int board[65][65];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
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
    isVisit[0][0] = true;

    bool flag = false;
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(board[curX][curY] == -1){
            flag = true;
            break;
        }

        int newX = curX + board[curX][curY];
        int newY = curY + board[curX][curY];

        if(newX < N && !isVisit[newX][curY]){
            bfsQ.push(make_pair(newX, curY));
            isVisit[newX][curY] = true;
        }

        if(newY < N && !isVisit[curX][newY]){
            bfsQ.push(make_pair(curX, newY));
            isVisit[curX][newY] = true;
        }
    }

    cout << (flag ? "HaruHaru" : "Hing") << "\n";

    return 0;
}

```