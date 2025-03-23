[문제 바로가기](https://boj.kr/19622)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[100001];

typedef struct {
    int from;
    int to;
    int member;
} meeting;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<meeting> arr;
    for(int i = 0; i < N; i++){
        int from, to, member;
        cin >> from >> to >> member;
        arr.push_back({from, to, member});
    }

    int ans = -1;
    dp[0] = arr[0].member;
    if(N > 0){
        ans = dp[0];
    }
    if(N > 1){
        dp[1] = arr[1].member;
    }

    for(int i = 2; i < N; i++){
        dp[i] = arr[i].member + ans;
        ans = max(dp[i - 1], ans);
    }

    ans = max(dp[N - 1], ans);
    cout << ans << "\n";

    return 0;
}

```