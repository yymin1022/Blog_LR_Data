[문제 바로가기](https://boj.kr/17451)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<double> arr;
    for (int i = 0; i < N; i++) {
        double input;
        cin >> input;
        arr.push_back(input);
    }

    double ans = arr.back();
    for (int i = N - 2; i >= 0; i--) {
        ans = ceil(ans / arr[i]) * arr[i];
    }

    cout << (long long)ans << "\n";

    return 0;
}
```