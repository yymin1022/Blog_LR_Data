[문제 바로가기](https://boj.kr/24516)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= 2 * N - 1; i += 2){
        cout << i << " ";
    }

    return 0;
}
```