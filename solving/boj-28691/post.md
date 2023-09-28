[문제 바로가기](https://boj.kr/28691)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    char C;
    cin >> C;

    if(C == 'M')
        cout << "MatKor" << "\n";
    else if(C == 'W')
        cout << "WiCys" << "\n";
    else if(C == 'C')
        cout << "CyKor" << "\n";
    else if(C == 'A')
        cout << "AlKor" << "\n";
    else
        cout << "$clear" << "\n";

    return 0;
}
```
