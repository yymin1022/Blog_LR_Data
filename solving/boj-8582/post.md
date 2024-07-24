[문제 바로가기](https://boj.kr/8582)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1000001][2];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> height;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        height.push_back(input);
    }

    dp[0][0] = height[0];
    for(int i = 1; i < N; i++){
        dp[i][0] = max(dp[i - 1][0], height[i]);
    }

    dp[N - 1][1] = height[N - 1];
    for(int i = N - 2; i >= 0; i--){
        dp[i][1] = max(dp[i + 1][1], height[i]);
    }

    for(int i = 0; i < N; i++){
        cout << dp[i][0] << " ";
        cout << dp[i][1] << "\n";
    }

    return 0;
}
```