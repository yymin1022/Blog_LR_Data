[문제 바로가기](https://boj.kr/5874)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int ans = 0;
    int cnt = 0;
    for(int i = 1; i < S.size(); i++){
        if(S[i] == '(' && S[i - 1] == '('){
            cnt++;
        }else if(S[i] == ')' && S[i - 1] == ')'){
            ans += cnt;
        }
    }

    cout << ans << "\n";

    return 0;
}
```