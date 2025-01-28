[문제 바로가기](https://boj.kr/1735)

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

    long long up1, down1, up2, down2;
    cin >> up1 >> down1 >> up2 >> down2;

    long long ansUp = down2 * up1 + up2 * down1;
    long long ansDown = down2 * down1;

    cout << ansUp / getGCD(ansUp, ansDown) << " ";
    cout << ansDown / getGCD(ansUp, ansDown) << "\n";


    return 0;
}
```