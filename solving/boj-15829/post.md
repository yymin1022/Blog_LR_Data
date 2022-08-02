[문제 바로가기](https://boj.kr/15829)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int L;
    string S;
    cin >> L >> S;

    long long result = 0;
    long long temp = 1;
    for(int i = 0; i < S.size(); i++){
        result += ((S[i] - 'a' + 1) * temp) % 1234567891;
        temp *= 31;
        temp %= 1234567891;
    }

    result %= 1234567891;

    cout << result << "\n";
    
    return 0;
}```