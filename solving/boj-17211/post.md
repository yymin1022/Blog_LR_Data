[문제 바로가기](https://boj.kr/17211)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

	double A, B, C, D;
    int N, cur;
	cin >> N >> cur >> A >> B >> C >> D;

	vector<double> bad;
	vector<double> good;
	if(cur == 0){
		bad.push_back(B);
		good.push_back(A);
	}else{
		bad.push_back(D);
		good.push_back(C);
	}

	for(int i = 1; i < N; i++){
		bad.push_back(good[i - 1] * B + bad[i - 1] * D);
		good.push_back(good[i - 1] * A + bad[i - 1] * C);
	}

	cout << fixed;
	cout.precision(0);
	cout << good[N - 1] * 1000 << "\n";
	cout << bad[N - 1] * 1000 << "\n";

    return 0;
}
```
