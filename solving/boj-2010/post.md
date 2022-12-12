[문제 바로가기](https://boj.kr/2010)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    int ans;
    cin >> ans;

    for(int i = 1; i < N; i++){
        int input;
        cin >> input;

        ans += input - 1;
    }

    cout << ans << "\n";

    return 0;
}
```