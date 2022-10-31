[문제 바로가기](https://boj.kr/15726)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    double A, B, C;
    cin >> A >> B >> C;

    cout << int(max(A * B / C, A / B * C)) << "\n";

    return 0;
}
```