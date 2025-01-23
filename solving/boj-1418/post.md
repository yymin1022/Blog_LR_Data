[문제 바로가기](https://boj.kr/1418)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    int ans = 0;
    for(int i = 1; i <= N; i++){
        int tmp = i;
        for(int j = 2; j <= K; j++){
            while(tmp % j == 0){
                tmp = tmp / j;
            }
        }

        if(tmp == 1){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```