[문제 바로가기](https://boj.kr/10992)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N - 1; i++){
        for(int j  = 1; j < N - i; j++){
            cout << " ";
        }

        if(i){
            cout << "*";
        }

        for(int j = 0; j < 2 * i - 1; j++){
            cout << " ";
        }

        cout << "*" << "\n";
    }

    for(int i = 0; i < 2 * N - 1; i++){
        cout << "*";
    }

    return 0;
}
```