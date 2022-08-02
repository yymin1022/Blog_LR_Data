[문제 바로가기](https://boj.kr/11726)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<int> dp;
    dp.push_back(1);
    dp.push_back(1);
    for(int i = 2; i <= 1000; i++){
        dp.push_back(dp[i - 1] + dp[i - 2]);
        dp[i] %= 10007;
    }

    int N;
    cin >> N;

    cout << dp[N] << "\n";

    return 0;
}```