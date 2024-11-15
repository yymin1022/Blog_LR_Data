[문제 바로가기](https://boj.kr/31867)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    string K;
    cin >> N >> K;

    int cnt[2] = {0, 0};
    for(int i = 0; i < N; i++){
        if(K[i] % 2 == 0){
            cnt[0]++;
        }else{
            cnt[1]++;
        }
    }

    cout << (cnt[0] == cnt[1] ? -1 : (cnt[0] < cnt[1] ? 1 : 0)) << "\n";

    return 0;
}
```
