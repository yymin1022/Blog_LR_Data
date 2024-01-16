[문제 바로가기](https://boj.kr/29807)

```c++
#include  <bits/stdc++.h>

using namespace std;

long long A, B, C, D, E;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    if(T >= 1){
        cin >> A;
    }
    if(T >= 2){
        cin >> B;
    }
    if(T >= 3){
        cin >> C;
    }
    if(T >= 4){
        cin >> D;
    }
    if(T >= 5){
        cin >> E;
    }

    long long ans = 0;
    if(A > C){
        ans += (A - C) * 508;
    }else{
        ans += (C - A) * 108;
    }

    if(B > D){
        ans += (B - D) * 212;
    }else{
        ans += (D - B) * 305;
    }

    ans += E * 707;

    cout << ans * 4763 << "\n";

    return 0;
}
```
