[문제 바로가기](https://boj.kr/26517)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long k, a, b, c, d;
    cin >> k >> a >> b >> c >> d;

    if(a * k + b == c * k + d){
        cout << "Yes " << a * k + b << "\n";
    }else{
        cout << "No" << "\n";
    }

    return 0;
}
```