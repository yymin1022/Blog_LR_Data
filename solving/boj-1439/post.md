[문제 바로가기](https://boj.kr/1439)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    string S;
    cin >> S;

    int cnt = 0;
    for(int i = 0; i < S.size(); i++){
        if(S[i] != S[i + 1]){
            cnt++;
        }
    }

    if(!cnt){
        cout << 0 << "\n";
    }else{
        cout << cnt / 2 << "\n";
    }

    return 0;
}
```