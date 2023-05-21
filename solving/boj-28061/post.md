[문제 바로가기](https://boj.kr/28061)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        ans = max(input - (N - i), ans);
    }

    cout << ans << "\n";

    return 0;
}
```