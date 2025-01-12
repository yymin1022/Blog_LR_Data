[문제 바로가기](https://boj.kr/9295)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 1; i <= T; i++){
        int A, B;
        cin >> A >> B;
        cout << "Case " << i << ": ";
        cout << A + B << "\n";
    }

    return 0;
}
```