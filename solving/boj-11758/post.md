[문제 바로가기](https://boj.kr/11758)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int x1, y1, x2, y2, x3, y3;
    cin >> x1 >> y1 >> x2 >> y2 >> x3 >> y3;

    int ccw = (x2 - x1) * (y3 - y1) - (x3 - x1) * (y2 - y1);
    if(ccw > 0){
        cout << 1 << "\n";
    }else if(ccw < 0){
        cout << -1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```