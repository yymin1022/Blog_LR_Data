[문제 바로가기](https://boj.kr/11943)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, C, D;
    cin >> A >> B >> C >> D;

    if(A + D > B + C){
        cout << B + C << "\n";
    }else{
        cout << A + D << "\n";
    }

    return 0;
}```