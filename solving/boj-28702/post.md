[문제 바로가기](https://boj.kr/28702)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string A, B, C;
    cin >> A >> B >> C;

    int ans;
    if(A[3] != 'z'){
        ans = stoi(A) + 3;
    }else if(B[3] != 'z'){
        ans = stoi(B) + 2;
    }else{
        ans = stoi(C) + 1;
    }

    if(ans % 3 == 0 && ans % 5 == 0){
        cout << "FizzBuzz" << "\n";
    }else if(ans % 3 == 0){
        cout << "Fizz" << "\n";
    }else if(ans % 5 == 0){
        cout << "Buzz" << "\n";
    }else{
        cout << ans << "\n";
    }

    return 0;
}

```
