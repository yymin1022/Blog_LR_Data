[문제 바로가기](https://boj.kr/14495)

```c++
#include  <bits/stdc++.h>

using namespace std;

long long dp[120];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 1;
    dp[3] = 1;
    for(int i = 4; i <= N; i++){
        dp[i] = dp[i - 1] + dp[i - 3];
    }

    cout << dp[N] << "\n";

    return 0;
}

```