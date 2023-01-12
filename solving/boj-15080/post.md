[문제 바로가기](https://boj.kr/15080)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int fromH, fromM, fromS;
    int toH, toM, toS;
    string tmp;

    cin >> fromH >> tmp >> fromM >> tmp >> fromS;
    cin >> toH >> tmp >> toM >> tmp >> toS;

    int from = fromH * 3600 + fromM * 60 + fromS;
    int to = toH * 3600 + toM * 60 + toS;

    int ans = to - from;
    if(ans < 0){
        ans += 86400;
    }

    cout << ans << "\n";

    return 0;
}
```