[문제 바로가기](https://boj.kr/14490)

```c++
#include <bits/stdc++.h>

using namespace std;

long long getGCD(long long A, long long B) {
    if(B > A){
        return getGCD(B, A);
    }else if(A % B == 0){
        return B;
    }else{
        return getGCD(B, A % B);
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int splitIdx = S.find(':');
    long long N = stoi(S.substr(0, splitIdx));
    long long M = stoi(S.substr(splitIdx + 1));

    long long gcd = getGCD(N, M);

    cout << N / gcd << ":";
    cout << M / gcd << "\n";
    
    return 0;
}
```