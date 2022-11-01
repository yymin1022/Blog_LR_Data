[문제 바로가기](https://boj.kr/10768)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int M, D;
    cin >> M >> D;

    if(M == 2 && D == 18){
        cout << "Special" << "\n";
    }else if(M == 2 && D < 18){
        cout << "Before" << "\n";
    }else if(M < 2){
        cout << "Before" << "\n";
    }else{
        cout << "After" << "\n";
    }

    return 0;
}
```