[문제 바로가기](https://boj.kr/2828)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, J;
    cin >> N >> M >> J;

    int ans = 0;
    int left = 1;
    int right = M;
    for(int i = 0; i < J; i++){
        int input;
        cin >> input;

        if(input < left){
            ans += left - input;
            left = input;
        }else if(input > left + M - 1){
            ans += input - (left + M - 1);
            left = input - M + 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```