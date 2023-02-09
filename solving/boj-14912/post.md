[문제 바로가기](https://boj.kr/14912)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, D;
    cin >> N >> D;

    int ans = 0;
    for(int i = 1; i <= N; i++){
        int tmp = i;
        while(tmp > 0){
            if(tmp % 10 == D){
                ans++;
            }
            tmp /= 10;
        }
    }

    cout << ans << "\n";

    return 0;
}
```