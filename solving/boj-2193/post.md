[문제 바로가기](https://boj.kr/2193)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[100];

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    dp[0] = 1;
    dp[1] = 1;
    for(int i = 2; i < N; i++){
        dp[i] = dp[i - 2] + dp[i - 1];
    }

    cout << dp[N - 1] << "\n";

    return 0;
}```