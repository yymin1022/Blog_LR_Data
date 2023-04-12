[문제 바로가기](https://boj.kr/1598)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    N--;
    M--;

    cout << abs(N / 4 - M / 4) + abs(N % 4 - M % 4) << "\n";

    return 0;
}
```