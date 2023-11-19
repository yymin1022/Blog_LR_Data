[문제 바로가기](https://boj.kr/11008)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        string S, P;
        cin >> S >> P;

        int ans = 0;
        int idx = 0;
        while(idx < S.size()){
            if (S.substr(idx, P.size()) == P){
                idx += P.size();
            }else{
                idx++;
            }
            ans++;
        }
        cout << ans << "\n";
    }

    return 0;
}
```