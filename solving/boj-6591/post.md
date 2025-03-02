[문제 바로가기](https://boj.kr/6591)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int N, K;
        cin >> N >> K;

        if(N == 0 && K == 0){
            break;
        }

        int R = N - K;
        if(K < R){
            swap(K, R);
        }

        int num = 1;
        long long ans = 1;
        for(int i = N; i >= N - R + 1; i--){
            ans *= i;
            ans /= num;
            num++;
        }

        cout << ans << "\n";
    }

    return 0;
}
```