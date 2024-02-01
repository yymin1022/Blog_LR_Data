[문제 바로가기](https://boj.kr/16237)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int A, B, C, D, E;
    cin >> A >> B >> C >> D >> E;

    int ans = 0;
    ans += E;

    ans += D;
    A = max(A - D, 0);

    ans += C;
    if(B < C){
        C -= B;
        A -= C * 2;
    }else {
        B -= C;
        ans += B / 2 + B % 2;
        A -= B / 2;
        if (B % 2) {
            A -= 3;
        }
    }
    if(A > 0){
        ans += A / 5;
        if(A % 5){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
