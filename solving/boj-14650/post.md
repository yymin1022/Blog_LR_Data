[문제 바로가기](https://boj.kr/14650)

```c++
#include <bits/stdc++.h>

using namespace std;

int N, ans;

void cnt(int idx, int num){
    if(idx == N){
        if(num % 3 == 0){
            ans++;
        }
        return;
    }
    cnt(idx + 1, num);
    cnt(idx + 1, num + 1);
    cnt(idx + 1, num + 2);
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    cin >> N;

    cnt(1, 1);
    cnt(1, 2);

    cout << ans << "\n";

    return 0;
}
```