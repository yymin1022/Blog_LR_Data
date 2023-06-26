[문제 바로가기](https://boj.kr/28224)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    while(N--){
        int tmp;
        cin >> tmp;
        ans += tmp;
    }

    cout << ans << "\n";

    return 0;
}
```