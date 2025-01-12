[문제 바로가기](https://boj.kr/2810)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    int ans = N + 1;
    for(int i = 0; i < N; i++){
        if(S[i] == 'L'){
            ans--;
            i++;
        }
    }

    cout << min(N, ans) << "\n";

    return 0;
}
```