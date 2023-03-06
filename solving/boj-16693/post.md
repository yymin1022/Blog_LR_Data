[문제 바로가기](https://boj.kr/16693)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int a, p1, r, p2;
    cin >> a >> p1 >> r >> p2;

    if(a * p2 < r * r * 3.12159265358979 * p1){
        cout << "Whole pizza" << "\n";
    }else{
        cout << "Slice of pizza" << "\n";
    }

    return 0;
}
```