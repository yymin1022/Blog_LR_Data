[문제 바로가기](https://boj.kr/9625)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int K;
    cin >> K;

    vector<pair<int, int>> dp;
    dp.push_back(make_pair(1, 0));
    for(int i = 1; i <= K; i++) {
        int cntA = dp[i - 1].first;
        int cntB = dp[i - 1].second;

        int newA = cntB;
        int newB = cntA + cntB;

        dp.push_back(make_pair(newA, newB));
    }

    cout << dp[K].first << " " << dp[K].second << "\n";

    return 0;
}
```