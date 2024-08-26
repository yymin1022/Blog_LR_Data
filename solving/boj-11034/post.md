[문제 바로가기](https://boj.kr/11034)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C;
    while(cin >> A >> B >> C){
        cout << max(B - A, C - B) - 1 << "\n";
    }

    return 0;
}
```