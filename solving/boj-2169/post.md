[문제 바로가기](https://boj.kr/2169)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[1001][1001];
int dp[1001][1001][3];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> arr[i][j];
        }
    }

    dp[0][0][0] = -987654321;
    dp[0][0][1] = arr[0][0];
    dp[0][0][2] = -987654321;

    for(int i = 1; i < M; i++){
        dp[0][i][0] = -987654321;
        dp[0][i][1] = -987654321;
        dp[0][i][2] = max(dp[0][i - 1][1], dp[0][i - 1][2]) + arr[0][i];
    }

    for(int i = 1; i < N; i++){
        for(int j = 0; j < M; j++){
            dp[i][j][1] = arr[i][j] + max(dp[i - 1][j][0], max(dp[i - 1][j][1], dp[i - 1][j][2]));
        }

        dp[i][0][2] = -987654321;
        for(int j = 1; j < M; j++){
            dp[i][j][2] = arr[i][j] + max(dp[i][j - 1][2], dp[i][j - 1][1]);
        }

        dp[i][M - 1][0] = -987654321;
        for(int j = M - 2; j >= 0; j--){
            dp[i][j][0] = arr[i][j] + max(dp[i][j + 1][0], dp[i][j + 1][1]);
        }
    }

    cout << max(dp[N - 1][M - 1][1], dp[N - 1][M - 1][2]) << "\n";

    return 0;
}
```