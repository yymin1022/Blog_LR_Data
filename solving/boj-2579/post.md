[문제 바로가기](https://boj.kr/2579)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> scores(N + 1, 0);
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        scores[i] = input;
    }

    vector<int> dp(N + 1, 0);
    dp[1] = scores[1];
    for(int i = 2; i <= N; i++){
        dp[i] = max(dp[i - 2], dp[i - 3] + scores[i - 1]) + scores[i];
    }

    cout << dp[N] << "\n";

    return 0;
}
```