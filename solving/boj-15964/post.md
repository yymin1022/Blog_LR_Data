[문제 바로가기](https://boj.kr/15964)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long A, B;
    cin >> A >> B;

    cout << (A + B) * (A - B) << "\n";
    
    return 0;
}```