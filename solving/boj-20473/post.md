[문제 바로가기](https://boj.kr/20473)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    while(N % 3){
        N -= 2;
        ans++;
    }

    cout << ans << " ";
    cout << N / 3 << "\n";

    return 0;
}
```