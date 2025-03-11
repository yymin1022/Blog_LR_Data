[문제 바로가기](https://boj.kr/25344)

```c++
#include <bits/stdc++.h>

using namespace std;

long long gcd(long long A, long long B){
    if(B == 0){
        return A;
    }

    return gcd(B, A % B);
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    long long ans = 1;
    for(int i = 0; i < N - 2; i++){
        long long input;
        cin >> input;

        ans *= input / gcd(ans, input);
    }

    cout << ans << "\n";

    return 0;
}
```