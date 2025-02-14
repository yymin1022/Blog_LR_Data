[문제 바로가기](https://boj.kr/2992)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    if(next_permutation(S.begin(), S.end())){
        cout << S << "\n";
    }else{
        cout << 0 << "\n";
    }

    return 0;
}
```