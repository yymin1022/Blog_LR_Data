[문제 바로가기](https://boj.kr/14470)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, C, D, E;
    cin >> A >> B >> C >> D >> E;

    int ans = 0;
    if(A < 0){
        ans += A * C * -1;
        A = 0;
    }

    if(A == 0){
        ans += D;
    }

    ans += (B - A) * E;

    cout << ans << "\n";

    return 0;
}
```