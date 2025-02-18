[문제 바로가기](https://boj.kr/4375)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    while(cin >> N){
        int digit = 1;
        int num = 1;
        while(num % N){
            digit++;

            num *= 10;
            num++;

            num %= N;
        }

        cout << digit << "\n";
    }

    return 0;
}
```