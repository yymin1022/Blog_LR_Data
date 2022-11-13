[문제 바로가기](https://boj.kr/1475)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string N;
    cin >> N;

    vector<int> cnt(10);
    for(int i = 0; i < N.size(); i++){
        cnt[N[i] - '0']++;
    }

    if((cnt[6] + cnt[9]) % 2) {
        cnt[6]++;
    }
    cnt[6] = (cnt[6] + cnt[9]) / 2;
    cnt[9] = cnt[6];

    int ans = *max_element(cnt.begin(), cnt.end());
    cout << ans << "\n";

    return 0;
}
```