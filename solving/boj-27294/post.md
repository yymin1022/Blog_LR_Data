[문제 바로가기](https://boj.kr/27294)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T, S;
    cin >> T >> S;

    if(T >= 12 && T <= 16 && S == 0){
        cout << 320 << "\n";
    }else{
        cout << 280 << "\n";
    }

    return 0;
}
```