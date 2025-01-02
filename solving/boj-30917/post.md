[문제 바로가기](https://boj.kr/30917)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    for(int A = 1; A <= 9; A++){
        cout << "? A " << A << endl;

        int res;
        cin >> res;

        if(res == 1){
            for(int B = 1; B <= 9; B++){
                cout << "? B " << B << endl;

                cin >> res;

                if(res == 1){
                    cout << "! " << A + B << endl;
                    return 0;
                }
            }
        }
    }

    return 0;
}

```
