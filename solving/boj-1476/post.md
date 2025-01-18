[문제 바로가기](https://boj.kr/147)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int E, S, M;
    cin >> E >> S >> M;

    int ans = 1;
    while(true){
        if((ans - E) % 15 == 0 && (ans - S) % 28==0 && (ans - M) % 19 == 0){
            break;
        }

		ans++;
    }

    cout << ans << "\n";

    return 0;
}

```
