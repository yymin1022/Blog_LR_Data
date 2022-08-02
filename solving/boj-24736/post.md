[문제 바로가기](https://boj.kr/24736)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T, F, S, P, C;
    cin >> T >> F >> S >> P >> C;
    T *= 6;
    F *= 3;
    S *= 2;
    C *= 2;
    cout << T + F + S + P + C << " ";

    cin >> T >> F >> S >> P >> C;
    T *= 6;
    F *= 3;
    S *= 2;
    C *= 2;
    cout << T + F + S + P + C << " ";

    return 0;
}
```