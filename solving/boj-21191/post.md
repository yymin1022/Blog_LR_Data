[문제 바로가기](https://boj.kr/21191)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<string> board;
    for(int i = 0; i < N; i++){
        string S;
        cin >> S;
        board.push_back(S);
    }

    int cnt = 0;
    for(int i = 0; i < N; i++){
        if(i == 0){
            for(int j = 0; j < N; j++){
                if(board[i][j] == 'B'){
                    cnt++;
                }
            }
        }else{
            int tmpH = 0;
            int tmpV = 0;
            for(int j = 0; j < N; j++){
                if(board[i][j] == 'B'){
                    tmpH++;
                }
                if(board[j][i] == 'B'){
                    tmpV++;
                }
            }

            if(cnt != tmpH || cnt != tmpV){
                cout << 0 << "\n";
                return 0;
            }
        }

        if(i > 1){
            for(int j = 2; j < N; j++){
                if(board[i][j] == board[i][j - 1] && board[i][j] == board[i][j - 2]){
                    cout << 0 << "\n";
                    return 0;
                }
                if(board[i][j] == board[i - 1][j] && board[i][j] == board[i - 2][j]){
                    cout << 0 << "\n";
                    return 0;
                }
            }
        }
    }

    cout << 1 << "\n";

    return 0;
}
```