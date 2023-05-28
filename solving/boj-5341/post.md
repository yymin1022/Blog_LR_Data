[문제 바로가기](https://boj.kr/5341)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    while(N){
        int sum = 0;
        for(int i = 1; i <= N; i++){
            sum += i;
        }

        cout << sum << "\n";

        cin >> N;
    }

    return 0;
}
```