[문제 바로가기](https://boj.kr/10996)

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
        for(int j = 0; j < N - N / 2; j++){
            cout << "*" << " ";
        }

        cout << "\n";

        for(int j = 0; j < N / 2; j++){
            cout << " " << "*";
        }

        cout << "\n";
    }

    return 0;
}
```