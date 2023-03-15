[문제 바로가기](https://boj.kr/21638)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int t1, v1, t2, v2;
    cin >> t1 >> v1 >> t2 >> v2;

    if(t2 < 0 && v2 >= 10){
        cout << "A storm warning for tomorrow! Be careful and stay home if possible!" << "\n";
    }else if(t2 < t1){
        cout << "MCHS warns! Low temperature is expected tomorrow." << "\n";
    }else if(v2 > v1){
        cout << "MCHS warns! Strong wind is expected tomorrow." << "\n";
    }else{
        cout << "No message" << "\n";
    }

    return 0;
}
```