[문제 바로가기](https://boj.kr/15486)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1510000];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr(1510000);
    for(int i = 0; i < N; i++){
        int T, P;
        cin >> T >> P;
        arr[i] = make_pair(T, P);
    }

    for(int i = 0; i < N; i++){
        dp[i + arr[i].first] = max(dp[i] + arr[i].second, dp[i + arr[i].first]);
        dp[i + 1] = max(dp[i], dp[i + 1]);
    }

    cout << dp[N] << "\n";

    return 0;
}

```