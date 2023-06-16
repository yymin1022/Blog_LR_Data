[문제 바로가기](https://boj.kr/27328)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    cout << ((A == B) ? 0 : ((A > B) ? 1 : -1)) << "\n";

    return 0;
}
```