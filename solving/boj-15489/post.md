[문제 바로가기](https://boj.kr/15489)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[40][40];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    for(int i = 1; i <= 31; i++){
        for(int j = 1; j <= i; j++){
            if(i == 1 || j == 1){
                dp[i][j] = 1;
            }else{
                dp[i][j] = dp[i - 1][j] + dp[i - 1][j - 1];
            }
        }
    }

    int R, C, W;
    cin >> R >> C >> W;

    int ans = 0;
    for(int i = R; i < R + W; i++){
        for(int j = C; j <= C + i - R; j++){
            ans += dp[i][j];
        }
    }

    cout << ans << "\n";

    return 0;
}

```