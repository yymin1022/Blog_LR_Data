[문제 바로가기](https://boj.kr/5612)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int ans = M;
    int S = M;
    for(int i = 0; i < N; i++){
        int in, out;
        cin >> in >> out;

        S += in;
        S -= out;

        if(S < 0){
            cout << 0 << "\n";
            return 0;
        }

        ans = max(S, ans);
    }

    cout << ans << "\n";

    return 0;
}
```