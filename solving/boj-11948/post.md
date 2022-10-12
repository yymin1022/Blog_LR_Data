[문제 바로가기](https://boj.kr/11948)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int minS = 100;
    int sum = 0;
    for(int i = 0; i < 4; i++){
        int input;
        cin >> input;
        minS = min(input, minS);
        sum += input;
    }

    sum -= minS;
    minS = 100;

    for(int i = 0; i < 2; i++){
        int input;
        cin >> input;

        minS = min(input, minS);
        sum += input;
    }

    sum -= minS;

    cout << sum << "\n";

    return 0;
}
```