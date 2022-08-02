[문제 바로가기](https://boj.kr/1012)

```c++
#include <bits/stdc++.h>

using namespace std;

void dfs(int, int);

int K, M, N, T;
int field[50][50];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> T;

    for(int i = 0; i < T; i++){
        memset(field, 0, sizeof(field));

        cin >> M >> N >> K;

        for(int j = 0; j < K; j++){
            int x, y;
            cin >> x >> y;
            field[x][y] = 1;
        }

        int cnt = 0;
        for(int j = 0; j < M; j++){
            for(int k = 0; k < N; k++){
                if(field[j][k] == 1){
                    dfs(j, k);
                    cnt++;
                }
            }
        }

        cout << cnt << "\n";
    }

    return 0;
}

void dfs(int x, int y){
    if(x < 0 || x >= M || y < 0 || y >= N || field[x][y] == 0){
        return;
    }

    field[x][y] = 0;
    dfs(x, y - 1);
    dfs(x, y + 1);
    dfs(x - 1, y);
    dfs(x + 1, y);
}```