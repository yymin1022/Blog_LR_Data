[문제 바로가기](https://boj.kr/17362)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N <= 5){
        cout << N << "\n";
        return 0;
    }

    if((N - 5) / 4 % 2) {
        cout << 1 + (N - 5) % 4 << "\n";
    }else {
        cout << 5 - (N - 5) % 4 << "\n";
    }

    return 0;
}
```