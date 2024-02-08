[문제 바로가기](https://boj.kr/14938)

```c++
#include  <bits/stdc++.h>

using namespace std;

int board[101][101];
int item[101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, R;
    cin >> N >> M >> R;

    for(int i = 1; i <= N; i++){
        cin >> item[i];
    }

    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            if(i == j){
                board[i][j] = 0;
            }else{
                board[i][j] = 987654321;
            }
        }
    }

    for(int i = 0; i < R; i++){
        int from, to, val;
        cin >> from >> to >> val;

        board[from][to] = val;
        board[to][from] = val;
    }

    for(int k = 1; k <= N; k++){
        for(int i = 1; i <= N; i++){
            for(int j = 1; j <= N; j++){
                board[i][j] = min(board[i][k] + board[k][j], board[i][j]);
            }
        }
    }

    int ans = 0;
    for(int i = 1; i <= N; i++){
        int tmp = 0;
        for(int j = 1; j <= N; j++){
            if(board[i][j] <= M){
                tmp += item[j];
            }
        }

        ans = max(tmp, ans);
    }

    cout << ans << "\n";

    return 0;
}
```
