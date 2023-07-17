[문제 바로가기](https://boj.kr/11060)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1101];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> maze;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        maze.push_back(input);
        dp[i] = N;
    }

    dp[0] = 0;
    for(int i = 0; i < N; i++){
        for(int j = 1; j <= maze[i]; j++){
            dp[i + j] = min(dp[i] + 1, dp[i + j]);
        }
    }

    cout << (dp[N - 1] < N ? dp[N - 1] : -1) << "\n";

    return 0;
}
```