[문제 바로가기](https://boj.kr/17247)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int x1 = -1, y1;
    int x2 = -1, y2;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            int input;
            cin >> input;

            if(input == 1){
                x1 == -1 ? x1 = i, y1 = j : x2 = i, y2 = j;
            }
        }
    }

    cout << abs(x2 - x1) + abs(y2 - y1) << "\n";

    return 0;
}
```