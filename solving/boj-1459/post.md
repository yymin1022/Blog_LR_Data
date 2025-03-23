[문제 바로가기](https://boj.kr/1459)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long X, Y, W, S;
    cin >> X >> Y >> W >> S;

    if(X > Y){
        swap(X, Y);
    }

    long long ans = min((X + Y) * W, X * S + (Y - X) * W);
    if((Y - X) % 2 == 1){
        ans = min((Y - 1) * S + W, ans);
    }else{
        ans = min(Y * S, ans);
    }

    cout << ans << "\n";

    return 0;
}
```