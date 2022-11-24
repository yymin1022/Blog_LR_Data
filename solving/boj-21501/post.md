[문제 바로가기](https://boj.kr/21501)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int wc, hc, ws, hs;
    cin >> wc >> hc >> ws >> hs;

    if(ws + 2 <= wc && hs + 2 <= hc){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```