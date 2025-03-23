[문제 바로가기](https://boj.kr/31263)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[5001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    dp[0] = 1;
    for(int i = 1; i < S.size(); i++){
        dp[i] = dp[i - 1] + 1;

        if(S[i - 1] != '0'){
            dp[i] = min(dp[i - 2] + 1, dp[i]);
        }

        if(S[i - 2] != '0' && S[i - 2] < '6'){
            dp[i] = min(dp[i - 3] + 1, dp[i]);
        }else if(S[i - 2] == '6' && S[i - 1] < '4'){
            dp[i] = min(dp[i - 3] + 1, dp[i]);
        }else if(S[i - 2] == '6' && S[i - 1] == '4' && S[i] <= '1'){
            dp[i] = min(dp[i - 3] + 1, dp[i]);
        }
    }

    cout << dp[N - 1] << "\n";

    return 0;
}
```
