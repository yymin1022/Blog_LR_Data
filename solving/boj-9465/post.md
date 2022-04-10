[문제 바로가기](https://boj.kr/9465)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[2][100001];
int sticker[2][100001];

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N, T;
    cin >> T;

    for(int t = 0; t < T; t++){
        cin >> N;

        for(int i = 0; i < 2; i++){
            for(int j = 0; j < N; j++){
                cin >> sticker[i][j];
                dp[i][j] = 0;
            }
        }

        dp[0][0] = sticker[0][0];
        dp[1][0] = sticker[1][0];
        dp[0][1] = dp[1][0] + sticker[0][1];
        dp[1][1] = dp[0][0] + sticker[1][1];
        for(int i = 2; i < N; i++){
            dp[0][i] = max(dp[1][i - 1], dp[1][i - 2]) + sticker[0][i];
            dp[1][i] = max(dp[0][i - 1], dp[0][i - 2]) + sticker[1][i];
        }

        int answer = max(dp[0][N - 1], dp[1][N - 1]);
        cout << answer << "\n";
    }

    return 0;
}
```