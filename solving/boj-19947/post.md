[문제 바로가기](https://boj.kr/19947)

```c++
#include <bits/stdc++.h>

using namespace std;

double dp[100001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    double H;
    int Y;
    cin >> H >> Y;

    dp[0] = H;
    for(int i = 1; i <= Y; i++){
        if(i >= 1){
            dp[i] = floor(max(dp[i - 1] * 1.05, dp[i]));
        }
        if(i >= 3){
            dp[i] = floor(max(dp[i - 3] * 1.2, dp[i]));
        }
        if(i >= 5){
            dp[i] = floor(max(dp[i - 5] * 1.35, dp[i]));
        }
    }

    cout << floor(dp[Y]) << "\n";

    return 0;
}
```