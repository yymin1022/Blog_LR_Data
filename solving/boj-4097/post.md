[문제 바로가기](https://boj.kr/4097)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    while(true){
        int N;
        cin >> N;

        if(N == 0){
            break;
        }

        int ans = -2147483648;
        int sum = 0;
        for(int i = 0; i < N; i++){
            int P;
            cin >> P;

            sum += P;
            ans = max(sum, ans);

            if(sum < 0){
                sum = 0;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```