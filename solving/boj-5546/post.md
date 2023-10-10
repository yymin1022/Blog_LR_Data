[문제 바로가기](https://boj.kr/5546)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[101][4][2];
int plan[101];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < K; i++){
        int A, B;
        cin >> A >> B;
        plan[A] = B;
    }

    if(plan[1] == 1){
        dp[1][1][0] = 1;
    }else if(plan[1] == 2){
        dp[1][2][0] = 1;
    }else if(plan[1] == 2){
        dp[1][3][0] = 1;
    }else{
        dp[1][1][0] = 1;
        dp[1][2][0] = 1;
        dp[1][3][0] = 1;
    }

    for(int i = 2; i <= N; i++){
        if(plan[i] == 1){
            dp[i][1][0] = (dp[i - 1][2][0] + dp[i - 1][2][1] + dp[i - 1][3][0] + dp[i - 1][3][1]) % 10000;
            dp[i][1][1] = dp[i - 1][1][0];
        }else if(plan[i] == 2){
            dp[i][2][0] = (dp[i - 1][1][0] + dp[i - 1][1][1] + dp[i - 1][3][0] + dp[i - 1][3][1]) % 10000;
            dp[i][2][1] = dp[i - 1][2][0];
        }else if(plan[i] == 3){
            dp[i][3][0] = (dp[i - 1][1][0] + dp[i - 1][1][1] + dp[i - 1][2][0] + dp[i - 1][2][1]) % 10000;
            dp[i][3][1] = dp[i - 1][3][0];
        }else{
            dp[i][1][0] = (dp[i - 1][2][0] + dp[i - 1][2][1] + dp[i - 1][3][0] + dp[i - 1][3][1]) % 10000;
            dp[i][1][1] = dp[i - 1][1][0];
            dp[i][2][0] = (dp[i - 1][1][0] + dp[i - 1][1][1] + dp[i - 1][3][0] + dp[i - 1][3][1]) % 10000;
            dp[i][2][1] = dp[i - 1][2][0];
            dp[i][3][0] = (dp[i - 1][1][0] + dp[i - 1][1][1] + dp[i - 1][2][0] + dp[i - 1][2][1]) % 10000;
            dp[i][3][1] = dp[i - 1][3][0];
        }
    }

    cout << (dp[N][1][0] + dp[N][1][1] + dp[N][2][0] + dp[N][2][1] + dp[N][3][0] + dp[N][3][1]) % 10000 << "\n";

    return 0;
}
```