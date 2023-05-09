[문제 바로가기](https://boj.kr/2616)

```c++
#include  <bits/stdc++.h>

using namespace std;

int arr[50001];
int dp[4][50001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N;

    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        arr[i] = arr[i - 1] + input;
    }

    cin >> K;

    for(int i = 1; i <= 3; i++){
        for(int j = i * K; j <= N; j++){
            dp[i][j] = max(dp[i][j - 1], dp[i - 1][j - K] + arr[j] - arr[j - K]);
        }
    }

    cout << dp[3][N] << "\n";

    return 0;
}
```