[문제 바로가기](https://boj.kr/25704)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, P;
    cin >> N >> P;

    int ans = P;
    if(N >= 20){
        ans = min(P * 3 / 4, ans);
    }
    if(N >= 15){
        ans = min(P - 2000, ans);
    }
    if(N >= 10){
        ans = min(P * 9 / 10, ans);
    }
    if(N >= 5){
        ans = min(P - 500, ans);
    }

    cout << (ans > 0 ? ans : 0) << "\n";

    return 0;
}
```