[문제 바로가기](https://boj.kr/7570)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[1000001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 1; i <= N; i++){
        int input;
        cin >> input;
        dp[input] = dp[input - 1] + 1;
        ans = max(dp[input], ans);
    }

    cout << N - ans << "\n";

    return 0;
}
```