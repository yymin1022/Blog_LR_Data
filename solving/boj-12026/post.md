[문제 바로가기](https://boj.kr/12026)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    for(int i = 0; i < N; i++){
        dp[i] = 987654321;
    }

    dp[0] = 0;
    for(int i = 1; i < N; i++){
        for(int j = 0; j < i; j++){
            if((S[j] == 'B' && S[i] == 'O') || (S[j] == 'O' && S[i] == 'J') || (S[j] == 'J' && S[i] == 'B')){
                dp[i] = min(dp[j] + (i - j) * (i - j), dp[i]);
            }
        }
    }

    cout << (dp[N - 1] == 987654321 ? -1 : dp[N - 1]) << "\n";

    return 0;
}

```
