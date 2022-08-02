[문제 바로가기](https://boj.kr/3036)

```c++
#include <bits/stdc++.h>

using namespace std;

int gcd(int, int);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, first;
    cin >> N >> first;

    for (int i = 0; i < N - 1; ++i) {
        int ring = 0;
        cin >> ring;
        
        int ans = gcd(first, ring);
        cout << first / ans << "/" << ring / ans << "\n";
    }

    return 0;
}

int gcd(int a, int b){
    if(b == 0){
        return a;
    }
    return gcd(b, a % b);
}```