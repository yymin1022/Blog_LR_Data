[문제 바로가기](https://boj.kr/1992)

```c++
#include <bits/stdc++.h>

using namespace std;

void check(int, int, int);

int N;
int video[65][65];

int main(){
    cin >> N;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        for(int j = 0; j < N; j++){
            video[j][i] = input[j] - '0';
        }
    }

    check(0, 0, N);

    return 0;
}

void check(int x, int y, int size){
    if(size == 1){
        cout << video[x][y];
        return;
    }

    bool isOK = true;
    int start = video[x][y];
    for(int i = 0; i < size; i++){
        for(int j = 0; j < size; j++){
            if(video[x + i][y + j] != start){
                cout << "(";
                check(x, y, size / 2);
                check(x + size / 2, y, size / 2);
                check(x, y + size / 2, size / 2);
                check(x + size / 2, y + size / 2, size / 2);
                cout << ")";

                isOK = false;
                i = size;
                j = size;
            }
        }
    }

    if(isOK){
        cout << start;
    }
}
```