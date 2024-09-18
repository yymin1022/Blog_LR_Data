[문제 바로가기](https://boj.kr/26099)

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
    while(N % 5){
        N -= 3;
        ans++;
    }

    if(N < 0){
        cout << -1 << "\n";
        return 0;
    }

    cout << ans + N / 5 << "\n";

    return 0;
}
```