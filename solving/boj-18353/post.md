[문제 바로가기](https://boj.kr/18353)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[2001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> soldier;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        soldier.push_back(input);
    }

    reverse(soldier.begin(), soldier.end());

    for(int i = 0; i < N; i++){
        dp[i] = 1;
        for(int j = 0; j <= i; j++){
            if(soldier[i] > soldier[j]){
                dp[i] = max(dp[j] + 1, dp[i]);
            }
        }
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        ans = max(dp[i], ans);
    }

    cout << N - ans << "\n";

    return 0;
}
```