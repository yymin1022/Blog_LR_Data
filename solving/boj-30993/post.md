[문제 바로가기](https://boj.kr/30993)

```c++
#include <bits/stdc++.h>

using namespace std;

long long factorial(long long N){
    long long res = 1;
    for(long long i = 1; i <= N; i++){
        res *= i;
    }

    return res;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N, A, B, C;
    cin >> N >> A >> B >> C;

    cout << factorial(N) / (factorial(A) * factorial(B) * factorial(C)) << "\n";

    return 0;
}
```
