[문제 바로가기](https://boj.kr/2643)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
	cin >> N;

	vector<pair<int,int>> arr;
	for(int i = 0; i < N; i++){
		int A, B;
		cin >> A >> B;

		arr.push_back(make_pair(min(A, B), max(A, B)));
	}

	sort(arr.begin(), arr.end());

	vector<int> dp(N, 1);
	for(int i = 1; i < N; i++){
		for(int j = 0; j < i; j++){
			if(arr[i].second >= arr[j].second){
				dp[i] = max(dp[i], dp[j] + 1);
			}
		}
	}

	cout << *max_element(dp.begin(), dp.end()) << "\n";

    return 0;
}

```
