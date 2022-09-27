[문제 바로가기](https://boj.kr/16199)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int birthY, birthM, birthD, Y, M, D;
    cin >> birthY >> birthM >> birthD >> Y >> M >> D;

    int age = Y - birthY;
    if(M < birthM || (M == birthM && D < birthD)){
        age--;
    }
    cout << age << "\n";

    age = Y - birthY + 1;
    cout << age << "\n";

    age = Y - birthY;
    cout << age << "\n";

    return 0;
}
```