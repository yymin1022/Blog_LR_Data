[문제 바로가기](https://boj.kr/2302)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[41];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    dp[0] = 1;
    dp[1] = 1;
    for(int i = 2; i <= N; i++){
        dp[i] = dp[i - 1] + dp[i - 2];
    }

    int ans = 1;
    int cur = 0;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;

        ans *= dp[input - cur  - 1];
        cur = input;
    }

    ans *= dp[N - cur];
    cout << ans << "\n";

    return 0;
}
```