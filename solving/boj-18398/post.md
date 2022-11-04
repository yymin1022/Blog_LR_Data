[문제 바로가기](https://boj.kr/18398)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        for(int i = 0; i < N; i++){
            long long A, B;
            cin >> A >> B;

            cout << A + B << " " << A * B << "\n";
        }
    }

    return 0;
}
```