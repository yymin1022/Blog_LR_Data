[문제 바로가기](https://boj.kr/6504)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[25];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    arr[1] = 1;
    arr[2] = 2;
    for(int i = 3; i <= 20; i++){
        arr[i] = arr[i - 1] + arr[i - 2];
    }

    int T;
    cin >> T;

    while(T--){
        int x;
        cin >> x;

        int ans = 0;
        for(int i = 20; i > 0; i--){
            if (x >= arr[i]){
                ans += arr[i - 1];
                x -= arr[i];
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```