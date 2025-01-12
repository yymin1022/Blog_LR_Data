[문제 바로가기](https://boj.kr/9063)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int maxX = -20000;
    int maxY = -20000;
    int minX = 20000;
    int minY = 20000;
    for(int i = 0; i < N; i++){
        int X, Y;
        cin >> X >> Y;

        maxX = max(X, maxX);
        maxY = max(Y, maxY);
        minX = min(X, minX);
        minY = min(Y, minY);
    }

    cout << (maxX - minX) * (maxY - minY) << "\n";

    return 0;
}
                                                                     
```