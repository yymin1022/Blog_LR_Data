[문제 바로가기](https://boj.kr/18242)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<string> board;
    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        board.push_back(S);
    }

    int leftX, leftY, rightX, rightY;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            if(board[i][j] == '#'){
                leftX = i;
                leftY = j;
                i = N;
                j = M;
            }
        }
    }

    for(int i = N - 1; i >= 0; i--){
        for(int j = M - 1; j >= 0; j--){
            if(board[i][j] == '#'){
                rightX = i;
                rightY = j;
                i = -1;
                j = -1;
            }
        }
    }

    int offset = (rightY - leftY + 1) / 2;
    if(board[leftX][leftY + offset] == '.'){
        cout << "UP" << "\n";
    }else if(board[leftX + offset][leftY] == '.'){
        cout << "LEFT" << "\n";
    }else if(board[rightX - offset][rightY] == '.'){
        cout << "RIGHT" << "\n";
    }else{
        cout << "DOWN" << "\n";
    }

    return 0;
}
```