[문제 바로가기](https://boj.kr/24568)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int R, S;
    cin >> R >> S;

    cout << R * 8 + S * 3 - 28 << "\n";
    
    return 0;
}```