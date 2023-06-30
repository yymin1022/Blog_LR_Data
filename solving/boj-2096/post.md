[문제 바로가기](https://boj.kr/2096)

```c++
#include <bits/stdc++.h>

using namespace std;

pair<int, int> dp[3];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        int x, y, z;
        cin >> x >> y >> z;

        if(i > 0){
            pair<int, int> tmpDP[3] = {dp[0], dp[1], dp[2]};
            pair<int, int> res;

            res.first = max(tmpDP[0].first, tmpDP[1].first) + x;
            res.second = min(tmpDP[0].second, tmpDP[1].second) + x;
            dp[0] = res;

            res.first = max(max(tmpDP[0].first, tmpDP[1].first), tmpDP[2].first) + y;
            res.second = min(min(tmpDP[0].second, tmpDP[1].second), tmpDP[2].second) + y;
            dp[1] = res;

            res.first = max(tmpDP[1].first, tmpDP[2].first) + z;
            res.second = min(tmpDP[1].second, tmpDP[2].second) + z;
            dp[2] = res;
        }else{
            dp[0] = make_pair(x, x);
            dp[1] = make_pair(y, y);
            dp[2] = make_pair(z, z);
        }
    }

    cout << max(max(dp[0].first, dp[1].first), dp[2].first) << " ";
    cout << min(min(dp[0].second, dp[1].second), dp[2].second) << " ";

    return 0;
}

```