[문제 바로가기](https://boj.kr/2303)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    int maxVal = 0;
    for(int i = 1; i <= N; i++){
        int a, b, c, d, e;
        cin >> a >> b >> c >> d >> e;

        int tmp = 0;
        tmp = max(tmp, (a + b + c) % 10);
        tmp = max(tmp, (a + b + d) % 10);
        tmp = max(tmp, (a + b + e) % 10);
        tmp = max(tmp, (a + c + d) % 10);
        tmp = max(tmp, (a + c + e) % 10);
        tmp = max(tmp, (a + d + e) % 10);
        tmp = max(tmp, (b + c + d) % 10);
        tmp = max(tmp, (b + c + e) % 10);
        tmp = max(tmp, (b + d + e) % 10);
        tmp = max(tmp, (c + d + e) % 10);

        if(maxVal <= tmp){
            maxVal = tmp;
            ans = i;
        }
    }

    cout << ans << "\n";

    return 0;
}
```