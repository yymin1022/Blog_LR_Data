[문제 바로가기](https://boj.kr/1783)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    if(N == 1){
        cout << 1 << "\n";
        return 0;
    }

    if(N == 2){
        cout << min((M - 1) / 2 + 1, 4) << "\n";
        return 0;
    }

    if(M >= 7){
        cout << M - 2 << "\n";
        return 0;
    }

    cout << min(M, 4) << "\n";

    return 0;
}
```