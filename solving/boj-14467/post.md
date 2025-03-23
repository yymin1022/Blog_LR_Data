[문제 바로가기](https://boj.kr/14467)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    vector<int> arr(100, -1);
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;

        if(arr[A] != -1 && arr[A] != B){
            ans++;
        }
        arr[A] = B;
    }

    cout << ans << "\n";

    return 0;
}
```