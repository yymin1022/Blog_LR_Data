[문제 바로가기](https://boj.kr/15228)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    int cnt = 1;

    while(cnt < N) {
        cnt *= 2;
        ans++;
    }

    ans += (N - cnt / 2 + cnt - 1) / cnt;

    cout << ans << "\n";

    return 0;
}
```