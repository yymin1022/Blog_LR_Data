[문제 바로가기](https://boj.kr/24228)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, R;
    cin >> N >> R;

    cout << N + R * 2 - 1 << "\n";

    return 0;
}
```