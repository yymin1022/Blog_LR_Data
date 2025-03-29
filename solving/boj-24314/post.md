[문제 바로가기](https://boj.kr/24314)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int a1, a0, c, n0;
    cin >> a1 >> a0 >> c >> n0;

    cout << (c <= a1 && c * n0 <= a1 * n0 + a0 ? 1 : 0) << "\n";

    return 0;
}
```