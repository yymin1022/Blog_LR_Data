[문제 바로가기](https://boj.kr/25784)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<int> num(3);
    cin >> num[0] >> num[1] >> num[2];

    sort(num.begin(), num.end());

    if (num[0] + num[1] == num[2])
        cout << 1 << "\n";
    else if (num[0] * num[1] == num[2])
        cout << 2 << "\n";
    else
        cout << 3 << "\n";

    return 0;
}
```