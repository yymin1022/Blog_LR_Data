[문제 바로가기](https://boj.kr/22864)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C, M;
    cin >> A >> B >> C >> M;

    int ans = 0;
    int sum = 0;
    for(int t = 0; t < 24; t++){
        if(sum + A > M){
            sum -= C;
            sum = max(sum, 0);
        }else{
            ans += B;
            sum += A;
        }
    }

    cout << ans << "\n";

    return 0;
}
```