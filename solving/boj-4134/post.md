[문제 바로가기](https://boj.kr/4134)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isPrime(long long num){
    if(num <= 1){
        return false;
    }

    if(num == 2 || num == 3){
        return true;
    }

    if(num % 2 == 0 || num % 3 == 0){
        return false;
    }

    for(long long i = 5; i * i <= num; i++){
        if(num % i == 0 || num % (i + 2) == 0){
            return false;
        }
    }

    return true;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    long long N;
    cin >> N;

    for(int i = 0; i < N; ++i){
        long long num;
        cin >> num;

        while(!isPrime(num)){
            num++;
        }

        cout << num << endl;
    }

    return 0;
}
```