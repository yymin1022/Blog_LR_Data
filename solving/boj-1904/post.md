[문제 바로가기](https://boj.kr/1904)

```c++
#include <bits/stdc++.h>

using namespace std;

int calc(int);

int dp[1000001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    dp[1] = 1;
    dp[2] = 2;

    cout << calc(N) << "\n";

    return 0;
}

int calc(int num){
    if(dp[num] == 0){
        dp[num] = (calc(num - 1) + calc(num - 2)) % 15746;
    }
    
    return dp[num];
}```