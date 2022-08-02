[문제 바로가기](https://boj.kr/25314)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    N /= 4;
    for(int i = 1; i < N; i++){
        cout << "long" << " ";
    }

    cout << "long int" << "\n";

    return 0;
}```