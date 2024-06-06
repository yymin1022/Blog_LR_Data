[문제 바로가기](https://boj.kr/1788)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp[1000001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

	int N;
	cin >> N;

	if(N < 0){
		cout << (N % 2 == 0 ? -1 : 1) << "\n";
		N *= -1;
	}else if(N > 0){
		cout << 1 << "\n";
	}else{
		cout << 0 << "\n";
	}

	dp[1] = 1;
	for(int i = 2; i <= N; i++){
		dp[i] = dp[i - 1] % 1000000000 + dp[i - 2] % 1000000000;
	}

	cout << dp[N] % 1000000000 << "\n";

    return 0;
}

```