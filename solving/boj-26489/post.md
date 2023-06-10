[문제 바로가기](https://boj.kr/26489)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int cnt = 0;
    while(true){
        string S;
        getline(cin, S);

        if(cin.eof() == 1){
            break;
        }
        cnt++;
    }

    cout << cnt << "\n";

    return 0;
}
```