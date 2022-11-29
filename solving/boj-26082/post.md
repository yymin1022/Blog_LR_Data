[문제 바로가기](https://boj.kr/26082)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    cin >> A >> B >> C;

    cout << (3 * B / A) * C << "\n";

    return 0;
}
```