[문제 바로가기](https://boj.kr/2294)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, K;
int dp[100001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    cin >> N >> K;

    vector<int> coin;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        coin.push_back(input);
    }

    if(K < coin[0]){
        cout << -1 << "\n";
        return 0;
    }

    for(int i = 0; i <= K; i++){
        dp[i] = 987654321;
    }

    for(int i = 0; i < N; i++){
        dp[coin[i]] = 1;
    }

    sort(coin.begin(), coin.end());

    for(int i = coin[0]; i <= K; i++){
        for(int j = 0; j < N; j++){
            if(i - coin[j] > 0){
                    dp[i] = min(dp[i - coin[j]] + 1, dp[i]);
            }
        }
    }

    if(dp[K] == 987654321){
        cout << -1 << "\n";
        return 0;
    }

    cout << dp[K] << "\n";

    return 0;
}
```