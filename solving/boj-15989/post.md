[문제 바로가기](https://boj.kr/15989)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[10005][3];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    dp[1][0] = 1;
    dp[2][0] = 1;
    dp[2][1] = 1;
    dp[3][0] = 1;
    dp[3][1] = 1;
    dp[3][2] = 1;
    for(int i = 4; i <= 10000; i++){
        dp[i][0] = 1;
        dp[i][1] = dp[i-2][0] + dp[i-2][1];
        dp[i][2] = dp[i-3][0] + dp[i-3][1] + dp[i-3][2];
    }

    int T;
    cin >> T;
    while(T--){
        int N;
        cin >> N;

        cout << dp[N][0] + dp[N][1] + dp[N][2] << "\n";
    }

    return 0;
}
```