[문제 바로가기](https://boj.kr/2624)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T, K;
    cin >> T >> K;

    vector<int> N;
    vector<int> P;
    for(int i = 0; i < K; i++){
        int p, n;
        cin >> p >> n;
        N.push_back(n);
        P.push_back(p);
    }

    dp[0] = 1;
    for(int i = 0; i < K; i++){
        for(int j = T; j >= 1; j--){
            int sum = 0;
            for(int k = 0; k < N[i]; k++){
                sum += P[i];
                if(j - sum >= 0 && dp[j-sum] > 0){
                    dp[j] += dp[j - sum];
                }
            }
        }
    }

    cout << dp[T] << "\n";

    return 0;
}

```