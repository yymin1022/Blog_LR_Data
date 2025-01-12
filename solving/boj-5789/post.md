[문제 바로가기](https://boj.kr/5789)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N--){
        string S;
        cin >> S;

        cout << (S[S.size() / 2 - 1] == S[S.size() / 2] ? "Do-it" : "Do-it-Not") << "\n";
    }

    return 0;
}
```
