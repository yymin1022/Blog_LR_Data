[문제 바로가기](https://boj.kr/17358)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    long long ans = 1;
    while(N > 0){
        ans *= N - 1;
        ans %= 1000000007;

        N -= 2;
    }

    cout << ans << "\n";

    return 0;
}
```