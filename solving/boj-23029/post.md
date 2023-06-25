[문제 바로가기](https://boj.kr/23029)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001][3];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> food;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        food.push_back(input);
    }

    dp[0][0] = 0;
    dp[0][1] = food[0] / 2;
    dp[0][2] = food[0];

    for(int i = 1; i < N; i++){
        dp[i][0] = max(max(dp[i - 1][0], dp[i - 1][1]), dp[i - 1][2]);
        dp[i][1] = dp[i - 1][2] + food[i] / 2;
        dp[i][2] = dp[i - 1][0] + food[i];
    }

    cout << max(max(dp[N - 1][0], dp[N - 1][1]), dp[N - 1][2]) << "\n";

    return 0;
}
```