[문제 바로가기](https://boj.kr/2156)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int drink[10001];
    for(int i = 1; i <= N; i++){
        cin >> drink[i];
    }

    int dp[10001];
    dp[1] = drink[1];
    dp[2] = drink[1] + drink[2];
    for(int i = 3; i <= N; i++){
        dp[i] = max(max(dp[i - 1], dp[i - 2] + drink[i]), dp[i - 3] + drink[i - 1] + drink[i]);
    }

    cout << dp[N] << "\n";

    return 0;
}```