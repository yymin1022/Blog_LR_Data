[문제 바로가기](https://boj.kr/24418)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[16][16];
int dp[31][31];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> arr[i][j];
        }
    }

    for(int i = 0; i < 31; i++){
        dp[i][0] = 1;
        dp[i][i] = 1;
    }

    for(int i = 2; i < 31; i++){
        for(int j = 1; j < i; j++){
            dp[i][j] = dp[i - 1][j - 1] + dp[i - 1][j];
        }
    }

    cout << dp[2 * N - 1][N] * 2 << " ";
    cout << N * N << "\n";

    return 0;
}
```