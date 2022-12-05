[문제 바로가기](https://boj.kr/10990)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 1; i <= N; i++){
        for(int j = 0; j < N - i; j++){
            cout << " ";
        }

        cout << "*";

        for(int j = 1; j < 2 * i - 2; j++){
            cout << " ";
        }

        if(i > 1){
            cout << "*";
        }

        cout << "\n";
    }

    return 0;
}
```