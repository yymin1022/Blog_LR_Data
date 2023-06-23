[문제 바로가기](https://boj.kr/15988)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[1000001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    dp[1] = 1;
    dp[2] = 2;
    dp[3] = 4;

    for(int i = 4; i <= 1000000; i++){
        dp[i] += dp[i - 1] + dp[i - 2] + dp[i - 3];
        dp[i] %= 1000000009;
    }

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;
        cout << dp[N] << "\n";
    }

    return 0;
}
```