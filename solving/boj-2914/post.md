[문제 바로가기](https://boj.kr/2914)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);
    
    int N, I;
    cin >> N >> I;

    cout << N * (I - 1) + 1 << "\n";

    return 0;
}
```