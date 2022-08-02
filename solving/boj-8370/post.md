[문제 바로가기](https://boj.kr/8370)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int n1, n2, k1, k2;
    cin >> n1 >> k1 >> n2 >> k2;
    cout << n1 * k1 + n2 * k2 << "\n";

    return 0;
}```