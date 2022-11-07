[문제 바로가기](https://boj.kr/25600)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 0; i < N; i++){
        int a, d, g;
        cin >> a >> d >> g;

        int temp = a * (d + g);

        if(a == d + g){
            temp *= 2;
        }

        ans = max(temp, ans);
    }

    cout << ans << "\n";

    return 0;
}
```