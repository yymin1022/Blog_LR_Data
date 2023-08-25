[문제 바로가기](https://boj.kr/28701)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans[2] = {0, 0};
    for(int i = 1; i <= N; i++){
        ans[0] += i;
        ans[1] += i * i * i;
    }

    cout << ans[0] << " ";
    cout << ans[0] * ans[0] << " ";
    cout << ans[1] << "\n";
    return 0;
}
```
