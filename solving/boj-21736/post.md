[문제 바로가기](https://boj.kr/21736)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[601][601];
char campus[601][601];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    queue<pair<int, int>> bfsQ;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < M; j++){
            campus[i][j] = input[j];

            if(campus[i][j] == 'I'){
                bfsQ.push(make_pair(i, j));
                isVisit[i][j] = true;
            }
        }
    }

    int cnt = 0;
    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(campus[curX][curY] == 'P'){
            cnt++;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= N || newY < 0 || newY >= M){
                continue;
            }

            if(!isVisit[newX][newY] && campus[newX][newY] != 'X'){
                bfsQ.push(make_pair(newX, newY));
                isVisit[newX][newY] = true;
            }
        }
    }

    if(cnt){
        cout << cnt << "\n";
    }else{
        cout << "TT" << "\n";
    }

    return 0;
}
```