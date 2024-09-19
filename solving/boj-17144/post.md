[문제 바로가기](https://boj.kr/17144)

```c++
#include <bits/stdc++.h>

using namespace std;

int air[1001][1001];
int tmp[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, C, T;
    cin >> R >> C >> T;

    bool isConditionerFound = false;
    int conditionerDown;
    int conditionerUp;
    int totalDust = 0;
    for(int i = 0; i < R; i++){
        for(int j = 0; j < C; j++){
            cin >> air[i][j];

            if(air[i][j] == -1){
                if(!isConditionerFound){
                    conditionerUp = i;
                    isConditionerFound = true;
                }else{
                    conditionerDown = i;
                }
            }else{
                totalDust += air[i][j];
            }
        }
    }

    while(T--){
        for(int i = 0; i < R; i++){
            for(int j = 0; j < C; j++){
                int cnt = 0;
                int val = air[i][j] / 5;

                if(air[i][j] <= 0){
                    continue;
                }

                int dx[4] = {0, 1, 0, -1};
                int dy[4] = {1, 0, -1, 0};
                for(int k = 0; k < 4; k++){
                    int newX = i + dx[k];
                    int newY = j + dy[k];
                    if (newX < 0 || newX >= R || newY < 0 || newY >= C || air[newX][newY] == -1){
                        continue;
                    }

                    tmp[newX][newY] += val;
                    cnt++;
                }

                tmp[i][j] -= (cnt * val);
            }
        }

        for(int i = 0; i < R; i++){
            for(int j = 0; j < C; j++){
                air[i][j] += tmp[i][j];
                tmp[i][j] = 0;
            }
        }

        totalDust -= air[conditionerDown + 1][0];
        totalDust -= air[conditionerUp - 1][0];

        for(int i = conditionerUp - 1; i > 0; i--){
            air[i][0] = air[i - 1][0];
        }

        for(int i = 0; i < C - 1; i++){
            air[0][i] = air[0][i + 1];
        }

        for(int i = 1; i <= conditionerUp; i++){
            air[i - 1][C - 1] = air[i][C - 1];
        }

        for(int i = C - 1; i > 1; i--){
            air[conditionerUp][i] = air[conditionerUp][i - 1];
        }

        air[conditionerUp][1] = 0;

        for(int i = conditionerDown + 1; i < R - 1; i++){
            air[i][0] = air[i + 1][0];
        }

        for(int i = 0; i < C - 1; i++){
            air[R - 1][i] = air[R - 1][i + 1];
        }

        for(int i = R - 1; i >= conditionerDown; i--){
            air[i][C - 1] = air[i - 1][C - 1];
        }

        for(int i = C - 1; i > 1; i--){
            air[conditionerDown][i] = air[conditionerDown][i - 1];
        }

        air[conditionerDown][1] = 0;
    }

    cout << totalDust << "\n";

    return 0;
}

```
