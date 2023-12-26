[문제 바로가기](https://boj.kr/8394)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> dp(10000001, -1);
    dp[1] = 1;
    dp[2] = 2;
    for(int i = 3; i <= N; i++){
        dp[i] = (dp[i - 1] + dp[i - 2]) % 10;
    }

    cout << dp[N] << "\n";

    return 0;
}
```