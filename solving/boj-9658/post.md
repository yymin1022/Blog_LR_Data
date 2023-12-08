[문제 바로가기](https://boj.kr/9658)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 0;
    dp[2] = 1;
    dp[3] = 0;
    dp[4] = 1;
    dp[5] = 1;
    for(int i = 6; i <= N; i++){
        if(dp[i - 1] == 1 && dp[i - 3] == 1 && dp[i - 4] == 1){
            dp[i] = 0;
        }else{
            dp[i] = 1;
        }
    }

    cout << (dp[N] == 1 ? "SK" : "CY") << "\n";

    return 0;
}
```