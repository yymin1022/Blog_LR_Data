[문제 바로가기](https://boj.kr/27971)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[100001];
int dp[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, A, B;
    cin >> N >> M >> A >> B;

    for(int i = 0; i < M; i++){
        int L, R;
        cin >> L >> R;
        arr[L]--;
        arr[R + 1]++;
    }

    for(int i = 0; i <= N; i++){
        arr[i] += arr[i - 1];
        dp[i] = 987654321;
    }

    dp[0] = 0;
    for(int i = 0; i <= N; i++){
        if(arr[i] < 0 || dp[i] == 987654321){
            continue;
        }

        if(i + A <= N){
            dp[i + A] = min(dp[i] + 1, dp[i + A]);
        }

        if(i + B <= N){
            dp[i + B] = min(dp[i] + 1, dp[i + B]);
        }
    }

    if(dp[N] == 987654321){
        cout << -1 << "\n";
    }else{
        cout << dp[N] << "\n";
    }

    return 0;
}

```