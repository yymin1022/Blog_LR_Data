[문제 바로가기](https://boj.kr/2903)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 2;
    for(int i = 1; i <= N; i++){
        ans += ans - 1;
    }

    cout << ans * ans << "\n";

    return 0;
}
```
