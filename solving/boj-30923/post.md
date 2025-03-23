[문제 바로가기](https://boj.kr/30923)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<long long> H;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        H.push_back(input);
    }

    long long ans = H[0] * 3 + 2;
    for(int i = 1; i < N; i++){
        ans += abs(H[i] - H[i - 1]) + H[i] * 2 + 2;
    }
    ans += H[N - 1];

    cout << ans << "\n";

    return 0;
}
```
