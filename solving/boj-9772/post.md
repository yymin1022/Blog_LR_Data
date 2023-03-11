[문제 바로가기](https://boj.kr/9772)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    float x, y;
    cin >> x >> y;

    while(x || y){
        if(x == 0 || y == 0){
            cout << "AXIS" << "\n";
        }else if(x > 0 && y > 0){
            cout << "Q1" << "\n";
        }else if(x < 0 && y > 0){
            cout << "Q2" << "\n";
        }else if(x < 0 && y < 0){
            cout << "Q3" << "\n";
        }else if(x > 0 && y < 0){
            cout << "Q4" << "\n";
        }
        cin >> x >> y;
    }

    cout << "AXIS" << "\n";

    return 0;
}
```