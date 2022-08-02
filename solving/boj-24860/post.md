[문제 바로가기](https://boj.kr/24860)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long v1, j1, v2, j2, v, d, j;
    cin >> v1 >> j1 >> v2 >> j2 >> v >> d >> j;
    cout << (v*j*d)*(v1*j1+v2*j2) << "\n";

    return 0;
}
```