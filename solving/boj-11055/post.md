[문제 바로가기](https://boj.kr/11055)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];
int nums[1001];

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> nums[i];
        dp[i] = nums[i];
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < i; j++){
            if(nums[j] < nums[i]){
                dp[i] = max(dp[j] + nums[i], dp[i]);
            }
        }
        ans = max(dp[i], ans);
    }

    cout << ans << "\n";

    return 0;
}
```