[문제 바로가기](https://boj.kr/11597)

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

    sort(arr.begin(), arr.end());

    int ans = 987654321;
    for(int i = 0; i < N  / 2; i++){
        ans = min(arr[i] + arr[N - 1 - i], ans);
    }

    cout << ans << "\n";

    return 0;
}
```