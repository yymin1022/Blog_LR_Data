[문제 바로가기](https://boj.kr/4172)

```c++
#include  <bits/stdc++.h>

using namespace std;

int dp[1000001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    dp[0] = 1;
    dp[1] = 1;
    for(int i = 1; i <= 1000000; i++){
        dp[i] = (dp[int(i - sqrt(i))] + dp[int(log(i))] + dp[int(i * sin(i) * sin(i))]) % 1000000;
    }

    int cur;
    cin >> cur;
    while(cur != -1){
        cout << dp[cur] << "\n";
        cin >> cur;
    }

    return 0;
}
```