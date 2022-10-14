[문제 바로가기](https://boj.kr/5717)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int M, F;
    cin >> M >> F;

    while(M && F){
        cout << M + F << "\n";

        cin >> M >> F;
    }

    return 0;
}
```