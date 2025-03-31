[문제 바로가기](https://boj.kr/11049)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[501][2];
int dp[501][501];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> arr[i][0] >> arr[i][1];
    }

    for(int i = 1; i < N; i++){
        for(int j = 0; j + i < N; j++){
            dp[j][j + i] = 2147483647;

            for(int k = 0; k <= i - 1; k++){
                dp[j][j + i] = min(dp[j][j + k] + dp[j + k + 1][j + i] + arr[j][0] * arr[j + k][1] * arr[j + i][1], dp[j][j + i]);
            }
        }
    }

    cout << dp[0][N - 1] << "\n";

    return 0;
}
```