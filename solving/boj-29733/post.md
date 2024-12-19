[문제 바로가기](https://boj.kr/29733)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[101][101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C, H;
    cin >> R >> C >> H;

    for(int i = 0; i < H; i++){
        for(int j = 0; j < R; j++){
            string input;
            cin >> input;

            for(int k = 0; k < C; k++){
                arr[i][j][k] = 0;
                if(input[k] == '*'){
                    arr[i][j][k] = -1;
                }
            }
        }
    }

    int dx[3] = {-1, 0, 1};
    int dy[9] = {-1, 0, 1, 1, 1, 0, -1, -1, 0};
    int dz[9] = {1, 1, 1, 0, -1, -1, -1, 0, 0};
    for(int i = 0; i < H; i++){
        for(int j = 0; j < R; j++){
            for(int k = 0; k < C; k++){
                if(arr[i][j][k] == -1){
                    for(int x = 0; x < 3; x++){
                        for(int yz = 0; yz < 9; yz++){
                            if(x == 1 && yz == 8){
                                continue;
                            }

                            int newX = i + dx[x];
                            int newY = j + dy[yz];
                            int newZ = k + dz[yz];

                            if(newX < 0 || newX >= H || newY < 0 || newY >= R || newZ < 0 || newZ >= C || arr[newX][newY][newZ] == -1){
                                continue;
                            }

                            arr[newX][newY][newZ]++;
                            arr[newX][newY][newZ] %= 10;
                        }
                    }
                }
            }
        }
    }

    for(int i = 0; i < H; i++){
        for(int j = 0; j < R; j++){
            for(int k = 0; k < C; k++){
                if(arr[i][j][k] == -1){
                    cout << "*";
                }else{
                    cout << arr[i][j][k];
                }
            }
            cout << "\n";
        }
    }

    return 0;
}
```
