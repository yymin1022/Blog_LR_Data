[문제 바로가기](https://boj.kr/26529)

```c++
#include <bits/stdc++.h>

using namespace std;

long long fibo[50];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    fibo[0] = 1;
    fibo[1] = 1;
    for(int i = 2; i < 50; i++){
        fibo[i] = fibo[i - 1] + fibo[i - 2];
    }

    while(N--){
        int X;
        cin >> X;
        cout << fibo[X] << "\n";
    }

    return 0;
}
```