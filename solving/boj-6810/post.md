[문제 바로가기](https://boj.kr/6810)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int X, Y, Z;
    cin >> X >> Y >> Z;

    cout << "The 1-3-sum is " << X + Y * 3 + Z + 91 << "\n";

    return 0;
}
```