[문제 바로가기](https://boj.kr/16486)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    double d1, d2;
    cin >> d1 >> d2;

    double ans = d1 * 2;
    ans += d2 * 2 * 3.141592;

    cout << fixed;
    cout.precision(6);
    cout << ans << "\n";

    return 0;
}
```