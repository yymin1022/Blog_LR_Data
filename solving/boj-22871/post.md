[문제 바로가기](https://boj.kr/22871)

```c++
#include <bits/stdc++.h>

using namespace std;

long long dp[5001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        arr.push_back(input);
    }

    dp[0] = 0;
    for(int i = 1; i < N; i++) {
        dp[i] = 987654321 * 2;
        for(int j = 0; j < i; j++) {
            dp[i] = min(max((i - j) * (1 + abs(arr[i] - arr[j])), dp[j]), dp[i]);
        }
    }

    cout << dp[N - 1];

    return 0;
}

```