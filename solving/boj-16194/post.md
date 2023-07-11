[문제 바로가기](https://boj.kr/16194)

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

    vector<int> cards(1001);
    for(int i = 1; i <= N; i++){
        cin >> cards[i];
    }

    for(int i = 1; i <= N; i++){
        dp[i] = cards[i];

        for(int j = 1; j < i; j++){
            dp[i] = min(dp[j] + dp[i - j], dp[i]);
        }
    }

    cout << dp[N] << "\n";

    return 0;
}

```