[문제 바로가기](https://boj.kr/3059)

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
        string S;
        cin >> S;

        int ans = 2015;
        vector<bool> flag(26, false);
        for(int i = 0; i < S.size(); i++){
            char cur = S[i];
            if(!flag[cur - 'A']){
                ans -= cur;
            }
            flag[cur - 'A'] = true;
        }

        cout << ans << "\n";
    }

    return 0;
}
```