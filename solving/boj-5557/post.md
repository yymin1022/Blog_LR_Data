[문제 바로가기](https://boj.kr/5557)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[21][101];

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

    dp[arr[0]][0] = 1;
    for(int i = 1;i < N - 1; i++){
        for(int j = 0; j <= 20; j++){
            if(dp[j][i - 1] > 0){
                if(0 <= j + arr[i] && j + arr[i] <= 20){
                    dp[j + arr[i]][i] += dp[j][i - 1];
                }
                if(0 <= j - arr[i] && j - arr[i] <= 20){
                    dp[j - arr[i]][i] += dp[j][i - 1];
                }
            }
        }
    }

    cout << dp[arr[N - 1]][N - 2];

    return 0;
}
```