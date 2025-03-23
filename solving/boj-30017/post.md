[문제 바로가기](https://boj.kr/30017)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    cout << (A > B ? B * 2 + 1 : A * 2 - 1) << "\n";

    return 0;
}
```
