[문제 바로가기](https://boj.kr/25625)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int x, y;
    cin >> x >> y;

    if(x > y){
        cout << x + y << "\n";
    }else{
        cout << y - x << "\n";
    }

    return 0;
}
```