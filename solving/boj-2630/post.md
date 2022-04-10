[문제 바로가기](https://boj.kr/2630)

```c++
#include <bits/stdc++.h>

using namespace std;

void check(int, int, int);

int N;
int paper[130][130];
int result[2];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> paper[i][j];
        }
    }

    check(0, 0, N);

    cout << result[0] << "\n" << result[1] << "\n";

    return 0;
}

void check(int x, int y, int size){
    int std = paper[x][y];
    for(int i = x; i < x + size; i++){
        for(int j = y; j < y + size; j++){
            if(paper[i][j] != std){
                check(x, y, size / 2);
                check(x, y + size / 2, size / 2);
                check(x + size / 2, y, size / 2);
                check(x + size / 2, y + size / 2, size / 2);
                return;
            }
        }
    }

    result[std]++;
}
```