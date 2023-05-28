[문제 바로가기](https://boj.kr/2720)

```c++

#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int C;
        cin >> C;

        cout << C / 25 << " ";
        C %= 25;

        cout << C / 10 << " ";
        C %= 10;

        cout << C / 5 << " ";
        C %= 5;

        cout << C << "\n";
    }

    return 0;
}
```