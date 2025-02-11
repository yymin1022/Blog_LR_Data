[문제 바로가기](https://boj.kr/3048)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N1, N2;
	cin >> N1 >> N2;

	vector<pair<char, int>> arr;

    string S;
	cin >> S;
	for(int i = N1 - 1; i >= 0; i--){
		arr.push_back(make_pair(S[i], 0));
	}

	cin >> S;
	for(int i = 0; i < N2; i++){
        arr.push_back(make_pair(S[i], 1));
	}

    int T;
	cin >> T;
    while(T--){
        for(int i = 0; i < N1 + N2 - 1; i++){
            if(arr[i].second == 0 && arr[i + 1].second == 1){
                swap(arr[i], arr[i + 1]);
                i++;
            }
        }
    }

	for(int i = 0; i < N1 + N2; i++){
		cout << arr[i].first;
	}
    cout << "\n";

    return 0;
}
```