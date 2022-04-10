[문제 바로가기](https://boj.kr/21300)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int sum = 0;
    for(int i = 0; i < 6; i++){
        int input;
        cin >> input;

        sum += input * 5;
    }

    cout << sum << "\n";

    return 0;
}
```