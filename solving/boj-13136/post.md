[문제 바로가기](https://boj.kr/13136)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long R, C, N;
    cin >> R >> C >> N;

    long long ans = 1;

    long long tmp = R / N;
    if(R % N){
        tmp++;
    }
    ans *= tmp;
    tmp = C / N;
    if(C % N){
        tmp++;
    }
    ans *= tmp;

    cout << ans << "\n";

    return 0;
}
```