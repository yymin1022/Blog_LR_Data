[문제 바로가기](https://boj.kr/25644)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int maxPrice = 0;
    for(int i = N - 1; i >= 0; i--){
        maxPrice = max(arr[i], maxPrice);
        ans = max(maxPrice - arr[i], ans);
    }

    cout << ans << "\n";

    return 0;
}
```