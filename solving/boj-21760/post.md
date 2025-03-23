[문제 바로가기](https://boj.kr/21760)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        long long N, M, K, D;
        cin >> N >> M >> K >> D;

        long long B = 0;
        while(N * M * B * (K  * (M - 1) + M * (N - 1)) / 2 <= D){
            B++;
        }

        if(B <= 1){
            cout << -1 << "\n";
        }else{
            cout << N * M * (B - 1) * (K * (M - 1) + M * (N - 1)) / 2 << "\n";
        }
    }

    return 0;
}
```