[문제 바로가기](https://boj.kr/20548)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    long long ans = 0;
    long long digit = 1;
    while(N){
        ans += (N % 7) * digit;
        digit *= 3;
        N /= 7;
    }

    cout << ans << "\n";

    return 0;
}
```