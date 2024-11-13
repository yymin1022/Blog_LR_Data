[문제 바로가기](https://boj.kr/6763)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, B;
    cin >> A >> B;

    B -= A;

    if(B > 30){
        cout << "You are speeding and your fine is $500." << "\n";
    }else if(B > 20){
        cout << "You are speeding and your fine is $270." << "\n";
    }else if(B > 0){
        cout << "You are speeding and your fine is $100." << "\n";
    }else{
        cout << "Congratulations, you are within the speed limit!" << "\n";
    }

    return 0;
}
```