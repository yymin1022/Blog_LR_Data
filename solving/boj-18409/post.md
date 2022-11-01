[문제 바로가기](https://boj.kr/18409)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    int N;
    string S;
    cin >> N >> S;

    int ans = 0;
    for(int i = 0; i < N; i++){
        char cur = S[i];
        if(cur == 'a' || cur == 'e' || cur == 'i' || cur == 'o' || cur == 'u'){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```