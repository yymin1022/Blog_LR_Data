[문제 바로가기](https://boj.kr/10870)

```c++
#include <bits/stdc++.h>

using namespace std;

int fibonacci(int n){
    if(n <= 1){
        return n;
    }else{
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    cout << fibonacci(N) << "\n";

    return 0;
}```