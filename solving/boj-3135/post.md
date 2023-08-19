[문제 바로가기](https://boj.kr/3135)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B, N;
    cin >> A >> B >> N;

    vector<int> button;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        button.push_back(input);
    }

    sort(button.begin(), button.end());

    int idx = lower_bound(button.begin(), button.end(), B) - button.begin();
    int ans = min(abs(button[idx] - B), abs(button[max(idx - 1, 0)] - B)) + 1;
    ans = min(abs(A - B), ans);

    cout << ans << "\n";

    return 0;
}
```