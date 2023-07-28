[문제 바로가기](https://boj.kr/1817)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int ans = 0;
    int cur = 0;
    for(int i = 0; i < N; i++){
        int book;
        cin >> book;

        cur += book;

        if(cur > M){
            ans++;
            cur = book;
        }
    }

    if(cur){
        ans++;
    }

    cout << ans << "\n";

    return 0;
}
```
