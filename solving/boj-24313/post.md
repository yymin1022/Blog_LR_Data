[문제 바로가기](https://boj.kr/24313)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A1, A0, C, N;
    cin >> A1 >> A0 >> C >> N;

    cout << ((A1 * N + A0 <= C * N && A1 <= C) ? 1 : 0) << "\n";

    return 0;
}
```