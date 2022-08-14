[문제 바로가기](https://boj.kr/2293)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> coin(N + 1);
    for(int i = 1; i <= N; i++){
        cin >> coin[i];
    }

    sort(coin.begin(), coin.end());

    dp[0] = 1;
    for(int i = 1; i <= N; i++){
        for(int j = coin[i]; j <= K; j++){
            dp[j] += dp[j - coin[i]];
        }
    }

    cout << dp[K] << "\n";

    return 0;
}
```