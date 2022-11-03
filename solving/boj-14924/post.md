[문제 바로가기](https://boj.kr/14924)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int S, T, D;
    cin >> S >> T >> D;

    cout << T * D / (S * 2) << "\n";

    return 0;
}
```