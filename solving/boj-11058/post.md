[문제 바로가기](https://boj.kr/11058)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i <= 6; i++){
        dp[i] = i;
    }

    for(int i = 7; i <= N; i++){
        dp[i] = dp[i - 1] + 1;

        for(int j = 3; j < i; j++){
            dp[i] = max(dp[i - j] * (j - 1), dp[i]);
        }
    }

    cout << dp[N] << "\n";

    return 0;
}
```