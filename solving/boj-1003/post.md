[문제 바로가기](https://boj.kr/1003)

```c++
#include <bits/stdc++.h>

using namespace std;

int fiboNums[41];
int fibonacci(int num){
    if(num <= 1){
        fiboNums[num] = num;
    }else if(fiboNums[num] == 0){
        fiboNums[num] = fibonacci(num - 1) + fibonacci(num - 2);
    }

    return fiboNums[num];
}

int main(){
    

    int T;
    cin >> T;

    for(int i = 0; i < T; i++){
        int N;
        cin >> N;

        if(N == 0){
            cout << 1 << " " << 0 << "\n";
        }else{
            cout << fibonacci(N - 1) << " " << fibonacci(N) << "\n";
        }
    }

    return 0;
}```