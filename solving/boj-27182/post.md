[문제 바로가기](https://boj.kr/27182)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    if(N < 8){
        cout << M + 7 << "\n";
    }else{
        cout << N - 7 << "\n";
    }

    return 0;
}
```