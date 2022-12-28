[문제 바로가기](https://boj.kr/7891)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        long long A, B;
        cin >> A >> B;

        cout << A + B << "\n";
    }

    return 0;
}
```