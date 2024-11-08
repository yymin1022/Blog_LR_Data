[문제 바로가기](https://boj.kr/19602)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int S, M, L;
    cin >> S >> M >> L;

    cout << (S + M * 2 + L * 3 >= 10 ? "happy" : "sad") << "\n";

    return 0;
}
```