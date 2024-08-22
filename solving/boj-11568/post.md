[문제 바로가기](https://boj.kr/11568)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        dp[i] = 1;
        for(int j = 0; j < i; j++){
            if(arr[j] < arr[i]) {
                dp[i] = max(dp[j] + 1, dp[i]);
            }
        }
        ans = max(dp[i], ans);
    }

    cout << ans << "\n";

    return 0;
}
```