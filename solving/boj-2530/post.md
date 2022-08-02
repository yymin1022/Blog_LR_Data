[문제 바로가기](https://boj.kr/2530)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C, D;
    cin >> A >> B >> C >> D;

    C += D;

    B += C / 60;
    C %= 60;

    A += B / 60;
    B %= 60;

    A %= 24;

    cout << A << " " << B << " " << C << "\n";
    
    return 0;
}```