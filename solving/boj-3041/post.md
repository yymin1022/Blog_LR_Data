[문제 바로가기](https://boj.kr/3041)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int ans = 0;
    for(int i = 0; i < 4; i++){
        for(int j = 0; j < 4; j++){
            char c;
            cin >> c;

            if(c == '.'){
                continue;
            }

            c -= 'A';
            ans += abs(c / 4 - i) + abs(c % 4 - j);
        }
    }

    cout << ans << "\n";

    return 0;
}
```