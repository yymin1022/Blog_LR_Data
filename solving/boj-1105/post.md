[문제 바로가기](https://boj.kr/1105)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string L, R;
    cin >> L >> R;
    if(L.length() != R.length()){
        cout << 0 << "\n";
        return 0;
    }

    int ans = 0;
    for(int i = 0; i < L.length(); i++){
        if(L[i] == R[i] && L[i] == '8') {
            ans++;
        }else if(L[i] != R[i]) {
            break;
        }
    }

    cout << ans << "\n";

    return 0;
}
```