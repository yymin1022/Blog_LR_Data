[문제 바로가기](https://boj.kr/3474)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        int cnt2 = 0;
        for(int i = 2; i <= N; i *= 2){
            cnt2 += N / i;
        }

        int cnt5 = 0;
        for(int i = 5; i <= N; i *= 5){
            cnt5 += N / i;
        }

        cout << min(cnt2, cnt5) << "\n";
    }

    return 0;
}
```