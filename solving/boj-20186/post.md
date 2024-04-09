[문제 바로가기](https://boj.kr/20186)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    for(int i = 1; i <= K; i++){
        ans += arr[N - i];
    }

    cout << ans - (K * (K - 1) / 2) << "\n";

    return 0;
}
```
