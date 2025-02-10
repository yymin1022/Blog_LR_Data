[문제 바로가기](https://boj.kr/17843)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cout << fixed;
    cout.precision(10);

    int T;
    cin >> T;
    while(T--){
        int h, m, s;
        cin >> h >> m >> s;

        vector<int> arr;
        arr.push_back(3600 * h + 60 * m + s);
        arr.push_back(720 * m + 12 * s);
        arr.push_back(720 * s);

        sort(arr.begin(), arr.end());

        float ans = min(min(arr[1] - arr[0], arr[2] - arr[1]), 43200 + arr[0] - arr[2]);
        cout << ans / 120 << "\n";
    }

    return 0;
}
```
