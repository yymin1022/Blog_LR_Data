[문제 바로가기](https://boj.kr/31408)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int maxCnt = 0;
    map<int, int> data;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        data[input]++;
        maxCnt = max(data[input], maxCnt);
    }

    cout << (N % 2 == 0 ? (maxCnt > N / 2 ? "NO" : "YES") : (maxCnt > N / 2 + 1 ? "NO" : "YES")) << "\n";

    return 0;
}
```
