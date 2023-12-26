[문제 바로가기](https://boj.kr/28444)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int H, I, A, R, C;
    cin >> H >> I >> A >> R >> C;

    cout << H * I - A * R * C << "\n";

    return 0;
}
```
