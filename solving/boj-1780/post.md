[문제 바로가기](https://boj.kr/1780)

```c++
#include <bits/stdc++.h>

using namespace std;

void check(int, int, int);

int N;
int cnt[3];
int paper[2200][2200];

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

    cout << cnt[0] << "\n";
    cout << cnt[1] << "\n";
    cout << cnt[2] << "\n";

    return 0;
}

void check(int x, int y, int width){
    if(width < 1){
        return;
    }

    bool isOK = true;
    int current = paper[x][y];
    for(int i = 0; i < width; i++){
        for(int j = 0; j < width; j++){
            if(paper[x + i][y + j] != current){
                check(x, y, width / 3);
                check(x, y + width / 3, width / 3);
                check(x, y + width / 3 * 2, width / 3);
                check(x + width / 3, y, width / 3);
                check(x + width / 3, y + width / 3, width / 3);
                check(x + width / 3, y + width / 3 * 2, width / 3);
                check(x + width / 3 * 2, y, width / 3);
                check(x + width / 3 * 2, y + width / 3, width / 3);
                check(x + width / 3 * 2, y + width / 3 * 2, width / 3);

                i = width;
                j = width;
                isOK = false;
            }
        }
    }

    if(isOK){
        cnt[current + 1]++;
    }
}
```