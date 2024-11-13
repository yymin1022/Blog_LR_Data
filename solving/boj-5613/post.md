[문제 바로가기](https://boj.kr/5613)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int ans;
    cin >> ans;
    while(true){
        string op;
        cin >> op;

        if(op == "="){
            cout << ans << "\n";
            break;
        }

        int num;
        cin >> num;
        if(op == "+"){
            ans += num;
        }else if(op == "-"){
            ans -= num;
        }else if(op == "*"){
            ans *= num;
        }else if(op == "/"){
            ans /= num;
        }
    }

    return 0;
}
```