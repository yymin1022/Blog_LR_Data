[문제 바로가기](https://boj.kr/27961)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    if(N == 0){
        cout << 0 << "\n";
        return 0;
    }

    long long ans = 1;
    long long cnt = 1;
    while(cnt < N){
        cnt *= 2;
        ans++;
    }

    cout << ans << "\n";

    return 0;
}
```