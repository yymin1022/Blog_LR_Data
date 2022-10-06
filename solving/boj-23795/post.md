[문제 바로가기](https://boj.kr/23795)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int sum = 0;
    while(true){
        int input;
        cin >> input;

        if(input < 0){
            break;
        }

        sum += input;
    }

    cout << sum << "\n";

    return 0;
}
```