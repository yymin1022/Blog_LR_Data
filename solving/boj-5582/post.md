[문제 바로가기](https://boj.kr/5582)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[4001][4001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string A, B;
    cin >> A >> B;

    int ans = 0;
    for(int i = 1; i <= A.size(); i++){
        for(int j = 1; j <= B.size(); j++){
            if(A[i - 1] == B[j - 1]){
                dp[i][j] = dp[i - 1][j - 1] + 1;
                ans = max(dp[i][j], ans);
            }
        }
    }

    cout << ans << "\n";

    return 0;
}

```