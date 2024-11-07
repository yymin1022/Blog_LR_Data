[문제 바로가기](https://boj.kr/30402)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    for(int i = 0; i < 15; i++){
        for(int j = 0; j < 15; j++){
            char input;
            cin >> input;

            switch(input){
                case 'w':
                    cout << "chunbae" << "\n";
                    return 0;
                case 'b':
                    cout << "nabi" << "\n";
                    return 0;
                case 'g':
                    cout << "yeongcheol" << "\n";
                    return 0;
            }
        }
    }

    return 0;
}
```
