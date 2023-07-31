[문제 바로가기](https://boj.kr/1072)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long X, Y;
    cin >> X >> Y;

    long long Z = Y * 100 / X;
    if(Z >= 99){
        cout << -1 << "\n";
        return 0;
    }

    long long left = 0;
    long long right = 1000000000;
    while(left <= right){
        long long mid = (left + right) / 2;
        long long newZ = (Y + mid) * 100 / (X + mid);

        if(Z < newZ){
            right = mid - 1;
        }else{
            left = mid + 1;
        }
    }

    cout << left << "\n";

    return 0;
}
```