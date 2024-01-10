[문제 바로가기](https://boj.kr/1120)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string A, B;
    cin >> A >> B;

    int ans = B.size();
    for(int i = 0; i < B.size() - A.size() + 1; i++){
        int cnt = 0;
        int idxB = i;
        for(int idxA = 0; idxA < A.size(); idxA++, idxB++){
            if(A[idxA] != B[idxB]){
                cnt++;
            }
        }
        ans = min(cnt, ans);
    }

    cout << ans << "\n";

    return 0;
}
```
