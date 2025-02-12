[문제 바로가기](https://boj.kr/10158)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int W, H, P, Q, T;
    cin >> W >> H >> P >> Q >> T;

    int tP = T % (W * 2);
    int tQ = T % (H * 2);

    int dir = 1;
    while(tP--){
        if(P == 0 || P == W){
            dir *= -1;
        }

        P += dir;
    }

    dir = 1;
    while(tQ--){
        if(Q == 0 || Q == H){
            dir *= -1;
        }

        Q += dir;
    }

    cout << P << " " << Q << "\n";

    return 0;
}
```