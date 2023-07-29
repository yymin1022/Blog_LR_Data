[문제 바로가기](https://boj.kr/2993)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    string ans = S;
    for (int i = 0; i < S.size() - 2; i++) {
        for (int j = i+1; j < S.size() - 1; j++) {
            string tmp = S;

            reverse(tmp.begin(), tmp.begin() + i + 1);
            reverse(tmp.begin() + i + 1, tmp.begin() + j + 1);
            reverse(tmp.begin() + j + 1, tmp.end());

            ans = min(tmp, ans);
        }
    }

    cout << ans << '\n';

    return 0;
}
```