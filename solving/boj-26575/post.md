[문제 바로가기](https://boj.kr/26575)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    double N;
    cin >> N;

    for(int i = 0; i < N; i++){
        double D, F, P;
        cin >> D >> F >> P;
        cout.precision(2);
        cout << fixed;
        cout << "$" << D * F * P << "\n";
    }

    return 0;
}
```