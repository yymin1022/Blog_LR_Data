[문제 바로가기](https://boj.kr/27433)

```c++
#include <bits/stdc++.h>

using namespace std;

long long fact(long long n){
    if(n <= 1){
        return 1;
    }
    return n * fact(n - 1);
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    cout << fact(N) << "\n";

    return 0;
}
```