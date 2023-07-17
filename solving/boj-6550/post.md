[문제 바로가기](https://boj.kr/6550)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string s, t;
    while(cin >> s >> t){
        if(s.size() > t.size()){
            cout << "No" << "\n";
            return 0;
        }

        int idx = 0;
        for(int i = 0; i < t.size(); i++){
            if(t[i] == s[idx]){
                idx++;
            }
        }

        cout << (idx == s.size() ? "Yes" : "No") << "\n";
    }

    return 0;
}
```