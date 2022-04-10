[문제 바로가기](https://boj.kr/1002)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int test = 0; test < T; test++){
        int x1, y1, r1, x2, y2, r2;
        cin >> x1 >> y1 >> r1 >> x2 >>y2 >> r2;
        
        int distance = (x1 - x2) * (x1 - x2) + (y1 - y2) * (y1 - y2);
        if(r1 == r2 && x1 == x2 && y1 == y2){
            cout << -1;
        }else if(distance > (r1 + r2) * (r1 + r2)){
            cout << 0;
        }else if(distance == (r1 + r2) * (r1 + r2)){
            cout << 1;
        }else{
            if(distance > (r2 - r1) * (r2 - r1)){
                cout << 2;
            }else if(distance == (r2 - r1) * (r2 - r1)){
                cout << 1;
            }else{
                cout << 0;
            }
        }

        cout << "\n";
    }

    return 0;
}
```