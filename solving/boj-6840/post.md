[문제 바로가기](https://boj.kr/6840)

```c++

#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int arr[3];
    cin >> arr[0] >> arr[1] >> arr[2];

    sort(arr, arr + 3);

    cout << arr[1] << "\n";

    return 0;
}
```