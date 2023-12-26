[문제 바로가기](https://boj.kr/4378)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string keyboard = "`1234567890-=QWERTYUIOP[]\\ASDFGHJKL;'ZXCVBNM,./";
    string S;

    while(getline(cin, S)) {
        for (char c: S) {
            if(c == ' '){
                cout << c;
            }else{
                for(int i = 0; i < keyboard.size(); i++){
                    if(keyboard[i] == c){
                        cout << keyboard[i - 1];
                    }
                }
            }
        }
        cout << "\n";
    }

    return 0;
}
```