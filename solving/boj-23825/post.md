[문제 바로가기](https://boj.kr/23825)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    cout << min(N / 2, M / 2) << "\n";

    return 0;
}
```