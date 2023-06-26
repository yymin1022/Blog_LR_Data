[문제 바로가기](https://boj.kr/17175)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[51];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N < 2){
        cout << 1 << "\n";
        return 0;
    }

    dp[0] = 1;
    dp[1] = 1;

    for(int i = 2; i <= N; i++){
        dp[i] = dp[i - 1] + dp[i - 2] + 1;
        dp[i] %= 1000000007;
    }

    cout << dp[N] << "\n";

    return 0;
}
```