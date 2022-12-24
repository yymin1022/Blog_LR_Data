[문제 바로가기](https://boj.kr/2935)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string A, B, op;
    cin >> A >> op >> B;

    string ans;
    int sizeA = A.length(), sizeB = B.length();
    if(op == "*"){
        ans = "1";

        for(int i = 0; i < sizeA - 1 + sizeB - 1; i++){
            ans += '0';
        }
    }else{
        if(sizeA == sizeB){
            ans = A;
            ans[0] = '2';
        }else{
            if(sizeA < sizeB){
                string tmp = A;
                A = B;
                B = tmp;
            }
            ans = A;
            ans[A.length() - B.length()] = '1';
        }
    }

    cout << ans << "\n";

    return 0;
}
```