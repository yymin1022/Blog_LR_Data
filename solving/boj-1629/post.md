[문제 바로가기](https://boj.kr/1629)

```c++
#include <bits/stdc++.h>

using namespace std;

int power(int, int);

int a,b,c;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    cin >> a >> b >> c;
    cout << power(a, b) << "\n";
}

int power(int n, int k){
    if(!k){
        return 1;
    }

    int temp = power(n, k / 2);
    int result = (1LL * temp * temp) % c;
    
   if(k % 2){
        result = 1LL * result * n % c;
    }

    return result;
}```