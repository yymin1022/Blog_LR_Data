[문제 바로가기](https://boj.kr/10824)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string A, B, C, D;
    cin >> A >> B >> C >> D;

    cout << stoll(A + B) + stoll(C + D) << "\n";

    return 0;
}
``