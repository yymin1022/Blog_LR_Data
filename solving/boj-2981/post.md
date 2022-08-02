[문제 바로가기](https://boj.kr/2981)

```c++
#include <bits/stdc++.h>

using namespace std;

int gcd(int, int);

int num[101];

int main(){
    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        cin >> num[i];
    }

    int M = 0;
    for(int i = 1; i < N; i++){
        M = gcd(abs(num[i] - num[i-1]), M);
    }

    set<int> result;
    for(int i = 1; i <= sqrt(M); i++){
        if(M % i == 0){
            result.insert(i);
            result.insert(M/i);
        }
    }

    for(auto temp : result){
        if(temp != 1){
            cout << temp << " ";
        }
    }
}

int gcd(int a, int b){
    if(b == 0){
        return a;
    }

    return gcd(b, a % b);
}```