[문제 바로가기](https://boj.kr/1535)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[21][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> L;
    L.push_back(0);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        L.push_back(input);
    }

    vector<int> J;
    J.push_back(0);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        J.push_back(input);
    }

    int ans = -1;
    for(int i = 1; i <= N; i++){
        for(int j = 100; j >= 0; j--){
            if(j - L[i] > 0){
                dp[i][j] = max(dp[i - 1][j], dp[i - 1][j - L[i]] + J[i]);
            }else{
                dp[i][j] = dp[i - 1][j];
            }
            ans = max(dp[i][j], ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```