[문제 바로가기](https://boj.kr/26005)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(N == 1){
        cout << 0 << "\n";
        return 0;
    }

    if(N % 2){
        cout << N * N / 2 + 1 << "\n";
    }else{
        cout << N * N / 2 << "\n";
    }

    return 0;
}
```