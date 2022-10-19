[문제 바로가기](https://boj.kr/19698)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, W, H, L;
    cin >> N >> W >> H >> L;

    int ans = min((W / L) * (H / L), N);
    cout << ans << "\n";

    return 0;
}
```