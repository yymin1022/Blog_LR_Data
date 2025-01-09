[문제 바로가기](https://boj.kr/30987)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    double x1, x2, a, b, c, d, e;
    cin >> x1 >> x2 >> a >> b >> c >> d >> e;

    cout << ((a / 3) * pow(x2, 3) + ((b - d) / 2) * pow(x2, 2) + (c - e) * x2)
        - ((a / 3) * pow(x1, 3) + ((b - d) / 2) * pow(x1, 2) + (c - e) * x1) << "\n";

    return 0;
}

```
