[문제 바로가기](https://boj.kr/14231)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[5001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> box;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        box.push_back(input);
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        dp[i] = 1;
        for(int j = 0; j < i; j++){
            if(box[j] < box[i]){
                dp[i] = max(dp[j] + 1, dp[i]);
            }
        }
        ans = max(dp[i], ans);
    }

    cout << ans << "\n";

    return 0;
}
```