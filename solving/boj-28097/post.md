[문제 바로가기](https://boj.kr/28097)

```c++

#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 8 * (N - 1);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        ans += input;
    }

    cout << ans / 24 << " ";
    cout << ans % 24 << "\n";

    return 0;
}
```