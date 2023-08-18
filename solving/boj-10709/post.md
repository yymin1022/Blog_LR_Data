[문제 바로가기](https://boj.kr/10709)

```c++
#include <bits/stdc++.h>

using namespace std;

char sky[101][101];
int res[101][101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int H, W;
    cin >> H >> W;

    for(int i = 0; i < H; i++){
        bool isCloud = false;
        for(int j = 0; j < W; j++){
            cin >> sky[i][j];

            res[i][j] = -1;
            if(sky[i][j] == 'c'){
                isCloud = true;
                res[i][j] = 0;
            }
        }
    }

    int time = 1;
    for(int k = 1; k < W; k++){
        for(int i = 0; i < H; i++){
            for(int j = W; j > 0; j--){
                if(sky[i][j - 1] == 'c' && res[i][j] == -1){
                    res[i][j] = time;
                    sky[i][j] = 'c';
                }
            }
        }
        time++;
    }

    for(int i = 0; i < H; i++){
        for(int j = 0; j < W; j++){
            cout << res[i][j] << " ";
        }
        cout << "\n";
    }

    return 0;
}

```