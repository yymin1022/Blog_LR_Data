[문제 바로가기](https://boj.kr/5893)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string N, tmp, ans;
    cin >> N;

    tmp = N;
    N += "0000";

    int c = 0;
    while(!tmp.empty()){
        int val = N.back() + tmp.back() - 48 * 2 + c;
        c = val / 2;
        ans += to_string(val % 2);
        N.pop_back();
        tmp.pop_back();
    }

    while(!N.empty()){
        int val = N.back() - 48 + c;
        c = val / 2;
        ans += to_string(val % 2);
        N.pop_back();
    }

    if(c){
        ans += "1";
    }

    reverse(ans.begin(), ans.end());
    cout << ans << "\n";

    return 0;
}
```