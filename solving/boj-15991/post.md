[문제 바로가기](https://boj.kr/15991)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    dp[0] = 1;
    dp[1] = 1;
    dp[2] = 2;
    dp[3] = 2;
    dp[4] = 3;
    dp[5] = 3;
    for(int i = 6; i <= 100000; i++){
        dp[i] = ((dp[i - 2] + dp[i - 4]) % 1000000009 + dp[i - 6]) % 1000000009;
    }

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        cout << dp[N] << "\n";
    }

    return 0;
}
```