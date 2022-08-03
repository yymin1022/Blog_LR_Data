[문제 바로가기](https://boj.kr/17386)

```c++
#include <bits/stdc++.h>

using namespace std;

struct point{
    long long x;
    long long y;
};

int CCW(point, point, point);

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    point A, B, C, D;
    cin >> A.x >> A.y >> B.x >> B.y;
    cin >> C.x >> C.y >> D.x >> D.y;

    int ccw1 = CCW(A, B, C) * CCW(A, B, D);
    int ccw2 = CCW(C, D, A) * CCW(C, D, B);

    if(ccw1 < 0 && ccw2 < 0){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}

int CCW(point A, point B, point C){
    long long val = A.x * B.y + B.x * C.y + C.x * A.y;
    val -= A.y * B.x + B.y * C.x + C.y * A.x;

    if(val > 0){
        return 1;
    }else if(val < 0){
        return -1;
    }else{
        return 0;
    }
}
```