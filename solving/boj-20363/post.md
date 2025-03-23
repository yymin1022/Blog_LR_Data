[문제 바로가기](https://boj.kr/20363)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int X, Y;
    cin >> X >> Y;
    if(X >= Y){
        cout << (X + Y) + Y / 10 << "\n";
    }else{
        cout << (X + Y) + X / 10 << "\n";
    }

    return 0;
}
```