[문제 바로가기](https://boj.kr/2875)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    while(K--){
        if(N > M * 2){
            N--;
        }else{
            M--;
        }
    }

    int ans = M;
    if(N < M * 2){
        ans = N / 2;
    }

    cout << ans << "\n";

    return 0;
}
```