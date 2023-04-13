[문제 바로가기](https://boj.kr/17387)

```c++
#include <iostream>

using namespace std;

struct point{
    long long x;
    long long y;
};

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

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    point A, B, C, D;
    cin >> A.x >> A.y >> B.x >> B.y;
    cin >> C.x >> C.y >> D.x >> D.y;

    int ccw1 = CCW(A, B, C);
    int ccw2 = CCW(A, B, D);
    int ccw3 = CCW(C, D, A);
    int ccw4 = CCW(C, D, B);

    if(ccw1 == 0 && ccw2 == 0 && ccw3 == 0 && ccw4 == 0){
        if((max(A.x, B.x) < min(C.x, D.x)) || (max(C.x, D.x) < min(A.x, B.x)) || (max(A.y, B.y) < min(C.y, D.y)) || (max(C.y, D.y) < min(A.y, B.y))){
            cout << 0 << "\n";
        }else{
            cout << 1 << "\n";
        }
    }else if(ccw1 * ccw2 <= 0 && ccw3 * ccw4 <= 0){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```