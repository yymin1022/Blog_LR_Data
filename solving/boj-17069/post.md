[문제 바로가기](https://boj.kr/17069)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[33][33];
long long dp[33][33][3];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> arr[i][j];
        }
    }

    dp[0][1][0] = 1;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if((i == 0 && j == 0) || arr[i][j] == 1){
                continue;
            }

            if(arr[i][j + 1] == 0){
                dp[i][j + 1][0] = dp[i][j][2] + dp[i][j][0];
            }

            if(arr[i + 1][j] == 0){
                dp[i + 1][j][1] = dp[i][j][2] + dp[i][j][1];
            }

            if(i + 1 < N && j + 1 < N){
                if(arr[i + 1][j] == 0 && arr[i][j + 1] == 0 && arr[i + 1][j + 1] == 0){
                    dp[i + 1][j + 1][2] = dp[i][j][0] + dp[i][j][1] + dp[i][j][2];
                }
            }
        }
    }

    cout << dp[N - 1][N - 1][0] + dp[N - 1][N - 1][1] + dp[N - 1][N - 1][2] << "\n";

    return 0;
}
```