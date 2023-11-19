[문제 바로가기](https://boj.kr/13301)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[100];

long long fibo(long long N){
    if(N <= 2){
        return dp[N] = 1;
    }

    if(dp[N] > 0){
        return dp[N];
    }

    return dp[N] = fibo(N - 1) + fibo(N - 2);
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long ans = 4;
    for(int i = 2; i <= N; i++){
        long long len = fibo(i);
        ans += len * 2;
    }

    cout << ans << "\n";

    return 0;
}
```