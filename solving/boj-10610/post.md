[문제 바로가기](https://boj.kr/10610)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string N;
    cin >> N;

    bool isZero = false;
    int num = 0;
    for(int i = 0; i < N.size(); i++){
        int cur = N[i] - '0';
        if(!cur){
            isZero = true;
        }
        num += cur;
    }

    sort(N.rbegin(), N.rend());

    if(isZero && !(num % 3)){
        cout << N << "\n";
    }else{
        cout << -1 << "\n";
    }

    return 0;
}
```