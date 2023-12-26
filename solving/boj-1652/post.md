[문제 바로가기](https://boj.kr/1652)

```c++
#include <bits/stdc++.h>

using namespace std;

char room[101][101];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < N; j++){
            room[i][j] = input[j];
        }
    }

    int cntH = 0;
    int cntV = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N - 1; j++){
            if(room[i][j] == '.' && room[i][j + 1] == '.' && (j + 2 == N || room[i][j + 2] == 'X')){
                cntV++;
            }
        }
        for(int j = 0; j < N - 1; j++){
            if(room[j][i] == '.' && room[j + 1][i] == '.' && (j + 2 == N || room[j + 2][i] == 'X')){
                cntH++;
            }
        }
    }

    cout << cntV << " ";
    cout << cntH << "\n";

    return 0;
}
```