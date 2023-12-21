[문제 바로가기](https://boj.kr/10707)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, C, D, P;
    cin >> A >> B >> C >> D >> P;

    if(P <= C){
        cout << min(P * A, B) << "\n";
    }else{
        cout << min(P * A, B + (P - C) * D) << "\n";
    }

    return 0;
}
```