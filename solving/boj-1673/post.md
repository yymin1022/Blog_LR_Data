[문제 바로가기](https://boj.kr/1673)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    while(cin >> N){
        cin >> K;

        int ans = 0;
        int stamp = 0;
        while(N){
            ans += N;
            stamp += N;

            N = stamp / K;
            stamp %= K;
        }

        cout << ans << "\n";
    }

    return 0;
}
```
