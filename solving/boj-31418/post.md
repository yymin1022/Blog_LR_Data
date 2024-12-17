[문제 바로가기](https://boj.kr/31418)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long W, H, K, T;
    cin >> W >> H >> K >> T;

    long long ans = 1;
    for(int i = 0; i < K; i++){
        long long x, y;
        cin >> x >> y;

        ans *= (min(W, x + T) - max(1ll, x - T) + 1) % 998244353;
        ans %= 998244353;
        ans *= (min(H, y + T) - max(1ll, y - T) + 1) % 998244353;
        ans %= 998244353;
    }

    cout << ans << "\n";

    return 0;
}
```
