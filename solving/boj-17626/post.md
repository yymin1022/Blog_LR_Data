[문제 바로가기](https://boj.kr/17626)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> dp(N + 1, 0);
    dp[1] = 1;
    for(int i = 2; i <= N; i++){
        int temp = 99999;
        for(int j = 1; j * j <= i; j++){
            int current = i - j * j;
            temp = min(temp, dp[current]);
        }
        dp[i] = temp + 1;
    }

    cout << dp[N] << "\n";

    return 0;
}```