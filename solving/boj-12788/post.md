[문제 바로가기](https://boj.kr/12788)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    vector<int> A;
	for (int i = 0; i < N; i++) {
        int input;
		cin >> input;
        A.push_back(input);
	}

	sort(A.begin(), A.end(), greater<int>());

    M *= K;
	int tmp=0;
	for (int i = 0; i < N; i++) {
		tmp += A[i];

		if(tmp >= M){
			cout << i + 1 << "\n";
			return 0;
		}
	}
	cout << "STRESS" << "\n";

    return 0;
}
```