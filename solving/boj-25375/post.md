[문제 바로가기](https://boj.kr/25375)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int Q; cin >> Q;
    while(Q--){
        long long A, B;
        cin >> A >> B;

        cout << ((B % A == 0 && A < B) ? 1 : 0) << "\n";
    }

    return 0;
}
```