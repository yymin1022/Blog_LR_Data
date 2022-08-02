[문제 바로가기](https://boj.kr/1799)

```c++
#include <bits/stdc++.h>
#include <iostream>

using namespace std;

int N;
int tempValue;
int returnValue[2];
int board[10][10];
int leftDiag[20];
int rightDiag[20];

void search(int, int, int, int);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> board[i][j];
        }
    }

    search(0, 0, 0, 0);
    search(1, 0, 0, 1);

    cout << returnValue[0] + returnValue[1] << "\n";
}

void search(int x, int y, int cnt, int isWhite){
    if(x >= N){
        x % 2 ? x = 0 : x = 1;
        y++;
    }

    if(y >= N){
        if(cnt > returnValue[isWhite]){
            returnValue[isWhite] = cnt;
        }
        return;
    }

    if(board[y][x] && !leftDiag[x - y + N - 1] && !rightDiag[x + y]){
        leftDiag[x - y + N - 1] = 1;
        rightDiag[x + y] = 1;

        search(x + 2, y, cnt + 1, isWhite);

        leftDiag[x - y + N - 1] = 0;
        rightDiag[x + y] = 0;
    }

    search(x + 2, y, cnt, isWhite);
}```