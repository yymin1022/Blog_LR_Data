[문제 바로가기](https://boj.kr/1057)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, A, B;
    cin >> N >> A >> B;

    int ans = 1;
    while(true){
        if(A % 2 == 1){
            A++;
        }

        if(B % 2 == 1){
            B++;
        }

        if(A == B){
            break;
        }

        ans++;
        A /= 2;
        B /= 2;
    }

    cout << ans << "\n";

    return 0;
}
```