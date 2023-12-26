[문제 바로가기](https://boj.kr/25707)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int maxNum = 0;
    int minNum = 2147483647;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        maxNum = max(input, maxNum);
        minNum = min(input, minNum);
    }

    cout << (maxNum - minNum) * 2 << "\n";

    return 0;
}
```