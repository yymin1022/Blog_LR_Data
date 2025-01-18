[문제 바로가기](https://boj.kr/12871)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S, T;
    cin >> S >> T;

    string tmpS;
    for(int i = 0; i < T.length(); i++){
        tmpS += S;
    }

    string tmpT;
    for(int i = 0; i < S.length(); i++){
        tmpT += T;
    }

    cout << (tmpS == tmpT ? 1 : 0) << "\n";

    return 0;
}
```