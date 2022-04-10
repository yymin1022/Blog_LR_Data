[문제 바로가기](https://boj.kr/17496)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, T, C, P;
    cin >> N >> T >> C >> P;

    int money = 0;
    while(N > T){
        money += C * P;
        N -= T;
    }

    cout << money << "\n";

    return 0;
}
```