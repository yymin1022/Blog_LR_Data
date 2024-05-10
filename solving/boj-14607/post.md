[문제 바로가기](https://boj.kr/14607)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    cout << (N * (N - 1)) / 2 << "\n";

    return 0;
}
```