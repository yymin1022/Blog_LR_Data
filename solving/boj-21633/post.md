[문제 바로가기](https://boj.kr/21633)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    float k;
    cin >> k;

    k /= 100;
    k += 25;

    cout.precision(2);
    cout << fixed;

    if(k < 100){
        cout << 100.0f << "\n";
    }else if(k > 2000){
        cout << 2000.0f << "\n";
    }else{
        cout << k << "\n";
    }

    return 0;
}
```