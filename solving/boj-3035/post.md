[문제 바로가기](https://boj.kr/3035)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int R, C, ZR, ZC;
    cin >> R >> C >> ZR >> ZC;

    for(int i = 0; i < R; i++){
        string input;
        cin >> input;

        for(int j = 0; j < ZR; j++){
            for(int k = 0; k < C; k++){
                for(int l = 0; l < ZC; l++){
                    cout << input[k];
                }
            }
            cout << "\n";
        }
    }

    return 0;
}****
```