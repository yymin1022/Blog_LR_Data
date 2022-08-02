[문제 바로가기](https://boj.kr/17256)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int Ax, Ay, Az, Cx, Cy, Cz;
    cin >> Ax >> Ay >> Az >> Cx >> Cy >> Cz;

    cout << Cx - Az << " " << Cy / Ay << " " << Cz - Ax << "\n";

    return 0;
}```