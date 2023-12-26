[문제 바로가기](https://boj.kr/2670)

```c++
#include  <bits/stdc++.h>

using namespace std;

double dp[10001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<double> arr;
    for(int i = 0; i < N; i++){
        double input;
        cin >> input;
        arr.push_back(input);
        dp[i] = input;
    }

    double ans = arr[0];
    for(int i = 1; i < N; i++){
        dp[i] = max(dp[i - 1] * arr[i], arr[i]);
        ans = max(dp[i], ans);
    }

    cout.precision(3);
    cout << fixed;
    cout << ans << "\n";

    return 0;
}
```