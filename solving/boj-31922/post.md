[문제 바로가기](https://boj.kr/31922)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, P, C;
    cin >> A >> P >> C;
    cout << max(A + C, P) << "\n";

    return 0;
}
```
