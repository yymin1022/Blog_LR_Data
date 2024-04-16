[문제 바로가기](https://boj.kr/2011)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[5001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    if(S[0] == '0'){
        cout << 0 << "\n";
        return 0;
    }

    dp[0] = 1;
    dp[1] = 1;
    for(int i = 2; i <= S.size(); i++){
        if(S[i - 1] != '0'){
            dp[i] = dp[i - 1] % 1000000;
        }

        if(S[i - 2] == '1' || (S[i - 2] == '2' && S[i - 1] <= '6')){
            dp[i] += dp[i - 2] % 1000000;
        }
    }

    cout << dp[S.size()] % 1000000 << "\n";

    return 0;
}

```
