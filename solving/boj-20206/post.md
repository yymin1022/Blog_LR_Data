[문제 바로가기](https://boj.kr/20206)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C, x1, x2, y1, y2;
    cin >> A >> B >> C >> x1 >> x2 >> y1 >> y2;

    int plus = 0;
    int minus = 0;
    int x[4] = {x1, x2, x1, x2};
    int y[4] = {y1, y2, y2, y1};
    for(int i = 0; i < 4; i++){
        int temp = A * x[i] + B * y[i] + C;

        if(!temp){
            minus = 0;
            plus = 0;
            break;
        }else if(temp > 0){
            plus++;
        }else{
            minus++;
        }
    }

    if(minus && plus){
        cout << "Poor" << "\n";
    }else{
        cout << "Lucky" << "\n";
    }

    return 0;
}```