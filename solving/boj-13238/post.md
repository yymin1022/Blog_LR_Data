[문제 바로가기](https://boj.kr/13238)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
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
    int minVal = arr[0];
    for(int i = 1; i < N; i++){
        minVal = min(arr[i], minVal);
        ans = max(arr[i] - minVal, ans);
    }

    cout << ans << "\n";

    return 0;
}
```