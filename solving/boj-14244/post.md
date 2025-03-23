[문제 바로가기](https://boj.kr/14244)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
	cin.tie(0);
	cout.tie(0);
	ios_base::sync_with_stdio(false);

	int N, M;
	cin >> N >> M;

	for(int i = 1; i <= M; i++){
		cout << 0 << " ";
		cout << i << "\n";
	}

	for(int i = M + 1; i < N; i++){
		cout << i - 1 << " ";
		cout << i << "\n";
	}

	return 0;
}
```
