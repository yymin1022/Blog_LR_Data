[문제 바로가기](https://boj.kr/1996)

```c++
#include <bits/stdc++.h>

using namespace std;

char mine[1001][1001];
int ans[1001][1001];

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
            mine[i][j] = input[j];

            if(mine[i][j] != '.'){
                int cnt = mine[i][j] - '0';
                int dx[8] = {0, 1, 1, 1, 0, -1, -1, -1};
                int dy[8] = {1, 1, 0, -1, -1, -1, 0, 1};
                for(int k = 0; k < 8; k++){
                    int newX = i + dx[k];
                    int newY = j + dy[k];
                    if(newX < 0 || newX >= N || newY < 0 || newY >= N){
                        continue;
                    }

                    ans[newX][newY] += cnt;
                }
            }
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(mine[i][j] != '.'){
                cout << "*";
            }else if(ans[i][j] < 10){
                cout << ans[i][j];
            }else{
                cout << "M";
            }
        }
        cout << "\n";
    }

    return 0;
}
```