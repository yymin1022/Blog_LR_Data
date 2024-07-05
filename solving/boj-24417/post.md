[문제 바로가기](https://boj.kr/24417)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int A = 1, B = 1;
    for (int i = 2; i < N; i++) {
        int tmp = B;
        B = (A + B) % 1000000007;
        A = tmp;
    }

    cout << B << " ";
    cout << N - 2 << "\n";

    return 0;
}
```