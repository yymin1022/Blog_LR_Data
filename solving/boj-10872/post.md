[문제 바로가기](https://boj.kr/10872)

```c++
#include <bits/stdc++.h>

using namespace std;

int factorial(int n){
    if(n <= 1){
        return 1;
    }else{
        return n * factorial(n - 1);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cout << factorial(N) << "\n";

    return 0;
}
```