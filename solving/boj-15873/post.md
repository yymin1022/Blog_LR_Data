[문제 바로가기](https://boj.kr/15873)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    int N;
    cin >> N;

    int A = 10;
    int B = 10;
    if(N < 100){
        A = N / 10;
        B = N % 10;
    }else if(N < 1000){
        if(N % 10){
            A = N / 10;
            B = N % 10;
        }else{
            A = N / 100;
            B = N % 100;
        }
    }

    cout << A + B << "\n";

    return 0;
}
```