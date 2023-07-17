[문제 바로가기](https://boj.kr/9656)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 0;
    dp[3] = 1;
    for(int i = 4; i <= N; i++){
        dp[i] = 1;
        if(dp[i - 1] == 1 || dp[i - 3] == 1){
            dp[i] = 0;
        }
    }

    cout << (dp[N] == 0 ? "SK" : "CY") << "\n";

    return 0;
}
```