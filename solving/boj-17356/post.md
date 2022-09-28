[문제 바로가기](https://boj.kr/17356)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    double M = (B - A) / (double)400;
    double ans = 1 / (1 + pow(10, M));

    cout << ans << "\n";

    return 0;
}
```