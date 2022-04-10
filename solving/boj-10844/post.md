[문제 바로가기](https://boj.kr/10844)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int dp[101][10];
    for(int i = 1; i < 10; i++){
        dp[1][i] = 1;
    }

    for(int i = 2; i <= 100; i++){
        for(int j = 0; j < 10; j++){
            if(j == 0){
                dp[i][j] = dp[i - 1][j + 1];
            }else if(j == 9){
                dp[i][j] = dp[i - 1][j - 1];
            }else{
                dp[i][j] = (dp[i - 1][j - 1] + dp[i - 1][j + 1]) % 1000000000;
            }
        }
    }

    int n;
    long long answer = 0;
    cin >> n;
    for(int i = 0; i < 10; i++){
        answer += dp[n][i];
    }

    cout << answer % 1000000000;

    return 0;
}
```