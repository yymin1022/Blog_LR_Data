[문제 바로가기](https://boj.kr/12785)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[201][201];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int W, H, X, Y;
    cin >> W >> H >> X >> Y;

    for(int i = 0; i < H; i++){
        dp[i][0] = 1;
    }

    for(int i = 0; i < W; i++){
        dp[0][i] = 1;
    }

    for(int i = 1; i < H; i++){
        for(int j = 1; j < W; j++){
            dp[i][j] = (dp[i - 1][j] + dp[i][j - 1]) % 1000007;
        }
    }

    cout << (dp[Y - 1][X - 1] * dp[H - Y][W - X]) % 1000007 << "\n";

    return 0;
}

```