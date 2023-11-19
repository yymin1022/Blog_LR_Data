[문제 바로가기](https://boj.kr/24508)

```c++
#include <bits/stdc++.h>

using namespace std;

int nadori[100001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K, T;
    cin >> N >> K >> T;

    long long sum = 0;
    for(int i = 0; i < N; i++){
        cin >> nadori[i];
        sum += nadori[i];
    }

    if(sum % K){
        cout << "NO" << "\n";
        return 0;
    }

    sort(nadori, nadori + N);

    long long cnt = 0;
    for(int i = 0; i < sum / K; i++){
        cnt += K - nadori[N - i - 1];
    }

    cout << (cnt <= T ? "YES" : "NO") << "\n";

    return 0;
}
```