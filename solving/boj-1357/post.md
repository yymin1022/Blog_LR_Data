[문제 바로가기](https://boj.kr/1357)

```c++
#include <bits/stdc++.h>

using namespace std;

int rev(int);

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int X, Y;
    cin >> X >> Y;

    cout << rev(rev(X) + rev(Y)) << "\n";

    return 0;
}

int rev(int num){
    int result = 0;

    while(num){
        result *= 10;
        result += num % 10;
        num /= 10;
    }

    return result;
}```