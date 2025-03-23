[문제 바로가기](https://boj.kr/32281)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[200001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    for(int i = 1; i <= N; i++){
        dp[i] = dp[i - 1] + i;
    }

    long long ans = 0;
    long long cnt = 0;
    for(int i = 0; i < N; i++){
        if(S[i] == '0'){
            ans += dp[cnt];
            cnt = 0;
        }else{
            cnt++;
        }
    }

    ans += dp[cnt];

    cout << ans << "\n";

    return 0;
}
```
