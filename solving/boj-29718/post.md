[문제 바로가기](https://boj.kr/29718)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> cnt(M + 1, 0);
    for(int i = 0; i < N; i++){
        for(int j = 1; j <= M; j++){
            int input;
            cin >> input;
            cnt[j] += input;
        }
    }

    for(int i = 1; i <= M; i++){
        cnt[i] += cnt[i - 1];
    }

    int A;
    cin >> A;

    int ans = 0;
    for(int i = A; i <= M; i++){
        ans = max(cnt[i] - cnt[i - A], ans);
    }

    cout << ans << "\n";

    return 0;
}
```
