[문제 바로가기](https://boj.kr/10988)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    for(int i = 0; i < S.size() / 2; i++){
        if(S[i] != S[S.size() - i - 1]){
            cout << 0 << "\n";
            return 0;
        }
    }

    cout << 1 << "\n";

    return 0;
}
```