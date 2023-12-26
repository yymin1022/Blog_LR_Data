[문제 바로가기](https://boj.kr/21612)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int B;
    cin >> B;

    B = B * 5 - 400;

    cout << B << "\n";
    cout << (B > 100 ? -1 : B < 100 ? 1 : 0) << "\n";

    return 0;
}
```
