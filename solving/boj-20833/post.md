[문제 바로가기](https://boj.kr/20833)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long ans = 0;
    for(int i = 1; i <= N; i++){
        ans += i * i * i;
    }

    cout << ans << "\n";

    return 0;
}
```