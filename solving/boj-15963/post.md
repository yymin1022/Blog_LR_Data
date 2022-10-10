[문제 바로가기](https://boj.kr/15963)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, M;
    cin >> N >> M;

    if(N == M){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```