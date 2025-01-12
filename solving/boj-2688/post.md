[문제 바로가기](https://boj.kr/2688)

```c++
#include <bits/stdc++.h>

using namespace std;

long long ans[65];
long long dp[10];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    dp[0] = 1;
    for(int i = 1; i < 65; i++){
        for(int j = 9; j > -1; j--){
            for(int k = 0; k < j; k++){
                dp[j] += dp[k];
            }
            ans[i] += dp[j];
        }
    }

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;
        cout << ans[N] << "\n";
    }

    return 0;
}

```