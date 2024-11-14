[문제 바로가기](https://boj.kr/31090)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        cout << ((N + 1) % (N % 100) == 0 ? "Good" : "Bye") << "\n";
    }

    return 0;
}
```
