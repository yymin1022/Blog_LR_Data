[문제 바로가기](https://boj.kr/11066)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[501][501];
int sum[501];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int K;
        cin >> K;

        for(int i = 1; i <= K; i++){
            int input;
            cin >> input;
            sum[i] = input + sum[i - 1];
        }

        for(int i = 1; i <= K; i++){
            for(int j = 1; j <= K - i; j++){
                dp[j][i + j] = 987654321;
                for(int k = j; k < i + j; k++){
                    dp[j][i + j] = min(dp[j][k] + dp[k + 1][i + j] + sum[i + j] - sum[j - 1], dp[j][i + j]);
                }
            }
        }

        cout << dp[1][K] << "\n";
    }

    return 0;
}

```