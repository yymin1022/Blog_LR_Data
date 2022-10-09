[문제 바로가기](https://boj.kr/13866)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C, D;
    cin >> A >> B >> C >> D;

    cout << abs(A + D - B - C) << "\n";

    return 0;
}
```