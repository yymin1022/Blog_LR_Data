[문제 바로가기](https://boj.kr/17404)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001][3];
int house[1001][3];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < 3; j++){
            cin >> house[i][j];
        }
    }

    int ans = 987654321;
    for(int i = 0; i < 3; i++){
        for(int j = 0; j < 3; j++){
            if(i == j){
                dp[0][j] = house[0][j];
            }else{
                dp[0][j] = 987654321;
            }
        }

        for(int j = 1; j < N; j++){
            dp[j][0] = house[j][0] + min(dp[j - 1][1], dp[j - 1][2]);
            dp[j][1] = house[j][1] + min(dp[j - 1][0], dp[j - 1][2]);
            dp[j][2] = house[j][2] + min(dp[j - 1][0], dp[j - 1][1]);
        }

        for(int j = 0; j < 3; j++){
            if(i != j){
                ans = min(dp[N - 1][j], ans);
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```