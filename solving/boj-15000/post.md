[문제 바로가기](https://boj.kr/15000)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    string S;
    cin >> S;

    for(int i = 0; i < S.size(); i++){
        cout << (char)(S[i] - 32);
    }

    return 0;
}
```