[문제 바로가기](https://boj.kr/1009)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        int a, b;
        cin >> a >> b;

        int value = 1;

        for(int i = 0; i < b; i++){
            value *= a;
            value %= 10;
        }

        if(value == 0){
            cout << 10 << "\n";
        }else{
            cout << value << "\n";
        }
    }

    return 0;
}
```