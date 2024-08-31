[문제 바로가기](https://boj.kr/28014)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, prev;
    cin >> N >> prev;

    int ans = 1;
    for(int i = 1; i < N; i++){
        int cur;
        cin >> cur;

        if(prev <= cur){
            ans++;
        }

        prev = cur;
    }

    cout << ans << "\n";

    return 0;
}
```