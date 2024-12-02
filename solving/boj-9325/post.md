[문제 바로가기](https://boj.kr/9325)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int S, N;
        cin >> S >> N;

        while(N--){
            int P, Q;
            cin >> P >> Q;
            S += P * Q;
        }

        cout << S << "\n";
    }

    return 0;
}
```