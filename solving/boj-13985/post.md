[문제 바로가기](https://boj.kr/13985)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    getline(cin, S);

    if(S[0] - '0' + S[4] - '0' == S[8] - '0'){
        cout << "YES" << "\n";
    }else{
        cout << "NO" << "\n";
    }

    return 0;
}
```