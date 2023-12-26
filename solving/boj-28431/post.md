[문제 바로가기](https://boj.kr/28431)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<bool> socks(10, false);
    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        socks[input] = socks[input] ? false : true;
    }
    for(int i = 0; i < 10; i++){
        if(socks[i]){
            cout << i << "\n";
        }
    }

    return 0;
}
```
