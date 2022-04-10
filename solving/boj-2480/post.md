[문제 바로가기](https://boj.kr/2480)

```c++
#include <bits/stdc++.h>

using namespace std;

int blockMap[501][501];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    cin >> A >> B >> C;

    int money = 0;
    if(A == B){
        if(B == C){
            money = 10000 + A * 1000;
        }else{
            money = 1000 + A * 100;
        }
    }else if(B == C){
        if(A == B){
            money = 10000 + A * 1000;
        }else{
            money = 1000 + B * 100;
        }
    }else if(A == C){
        if(A == B){
            money = 10000 + A * 1000;
        }else{
            money = 1000 + A * 100;
        }
    }else{
        if(A > B){
            if(A > C){
                money = A * 100;
            }else{
                money = C * 100;
            }
        }else{
            if(B > C){
                money = B * 100;
            }else{
                money = C * 100;
            }
        }
    }

    cout << money << "\n";

    return 0;
}
```