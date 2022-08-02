[문제 바로가기](https://boj.kr/4153)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(1){
        int A, B, C, M;
        cin >> A >> B >> C;

        if(A == 0 && B == 0 && C == 0){
            break;
        }

        string result;
        if(A > B){
            if(A > C){
                A * A == B * B + C * C ? result = "right" : result = "wrong";
            }else{
                C * C == A * A + B * B ? result = "right" : result = "wrong";
            }
        }else{
            if(B > C){
                B * B == A * A + C * C ? result = "right" : result = "wrong";
            }else{
                C * C == A * A + B * B ? result = "right" : result = "wrong";
            }
        }

        cout << result << "\n";
    }
    
    return 0;
}```