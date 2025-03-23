[문제 바로가기](https://boj.kr/23560)

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
    for(int i = 2; i <= N; i++){
        ans *= 3;
    }

    cout << ans << "\n";

    return 0;
}
```