[문제 바로가기](https://boj.kr/14500)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int board[501][501];
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> board[i][j];
        }
    }

    int answer = 0;
    for(int i = 0; i < N - 3; i++){
        for(int j = 0; j < M; j++){
            answer = max(answer, board[i][j] + board[i + 1][j] + board[i + 2][j] + board[i + 3][j]);
        }
    }
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M - 3; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i][j + 2] + board[i][j + 3]);
        }
    }

    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i + 1][j] + board[i + 1][j + 1]);
        }
    }

    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i][j + 2] + board[i + 1][j]);
        }
    }
    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 1][j + 2]);
        }
    }
    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i][j + 2] + board[i + 1][j + 2]);
        }
    }
    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j + 2] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 1][j + 2]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i + 1][j] + board[i + 2][j]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i + 1][j] + board[i + 2][j] + board[i + 2][j + 1]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i + 1][j + 1] + board[i + 2][j + 1]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j + 1] + board[i + 1][j + 1] + board[i + 2][j] + board[i + 2][j + 1]);
        }
    }

    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i + 1][j + 1] + board[i + 1][j + 2]);
        }
    }
    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j + 1] + board[i][j + 2] + board[i + 1][j] + board[i + 1][j + 1]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 2][j + 1]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j + 1] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 2][j]);
        }
    }

    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j] + board[i][j + 1] + board[i][j + 2] + board[i + 1][j + 1]);
        }
    }
    for(int i = 0; i < N - 1; i++){
        for(int j = 0; j < M - 2; j++){
            answer = max(answer, board[i][j + 1] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 1][j + 2]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 2][j]);
        }
    }
    for(int i = 0; i < N - 2; i++){
        for(int j = 0; j < M - 1; j++){
            answer = max(answer, board[i][j + 1] + board[i + 1][j] + board[i + 1][j + 1] + board[i + 2][j + 1]);
        }
    }

    cout << answer << "\n";

    return 0;
}
```