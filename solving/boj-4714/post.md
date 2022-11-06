[문제 바로가기](https://boj.kr/4714)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    double X;
    cin >> X;

    while(X >= 0){
        cout << fixed;
        cout.precision(2);

        cout << "Objects weighing " << X <<  " on Earth will weigh " << X * 0.167 << " on the moon." << "\n";

        cin >> X;
    }

    return 0;
}
```