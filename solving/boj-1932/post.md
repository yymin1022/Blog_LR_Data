[문제 바로가기](https://boj.kr/1932)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    int dp[501][501];
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= i; j++){
            cin >> dp[i][j];
        }
    }

    for(int i = 2; i <= N; i++){
        dp[i][1] += dp[i - 1][1];
        for(int j = 2; j < i; j++){
            dp[i][j] += max(dp[i - 1][j - 1], dp[i - 1][j]);
        }
        dp[i][i] += dp[i - 1][i - 1];
    }

    int answer = 0;
    for(int i = 1; i <= N; i++){
        answer = max(answer, dp[N][i]);
    }

    cout << answer << "\n";

    return 0;
}```