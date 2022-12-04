[문제 바로가기](https://boj.kr/26209)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 8; i++){
        int input;
        cin >> input;

        if(input == 9){
            cout << "F" << "\n";
            return 0;
        }
    }

    cout << "S" << "\n";

    return 0;
}
```