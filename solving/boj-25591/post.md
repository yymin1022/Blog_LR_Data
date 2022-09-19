[문제 바로가기](https://boj.kr/25591)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int X, Y;
    cin >> X >> Y;

    int a = 100 - X;
    int b = 100 - Y;
    int c = 100 - (a + b);
    int d = a * b;
    int q = d / 100;
    int r = d % 100;

    cout << a << " ";
    cout << b << " ";
    cout << c << " ";
    cout << d << " ";
    cout << q << " ";
    cout << r << "\n";

    c += q;

    cout << c << " ";
    cout << r << "\n";

    return 0;
}
```