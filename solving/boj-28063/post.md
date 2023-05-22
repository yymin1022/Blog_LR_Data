[문제 바로가기](https://boj.kr/28063)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, x, y;
    cin >> N >> x >> y;

    if(N == 1 && x == 1 && y == 1){
        cout << 0 << "\n";
    }else if(N == 1){
        cout << 1 << "\n";
    }else if((x == 1 && y == 1) || (x == 1 && y == N) || (x == N && y == 1) || (x == N && y == N)){
        cout << 2 << "\n";
    }else if(x == 1 || y == 1 || x == N || y == N){
        cout << 3 << "\n";
    }else{
        cout << 4 << "\n";
    }

    return 0;
}
```