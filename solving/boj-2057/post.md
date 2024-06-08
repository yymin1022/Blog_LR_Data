[문제 바로가기](https://boj.kr/2057)

```c++
#include <bits/stdc++.h>

using namespace std;

long long factorial[20];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    factorial[0] = 1;
    for(long long i = 1; i < 20; i++){
        factorial[i] = factorial[i - 1] * i;
    }

    long long N;
    cin >> N;

    if(N == 0){
        cout << "NO" << "\n";
    }else{
        for(int i = 19; i >= 0; i--){
            if(N >= factorial[i]){
                N -= factorial[i];
            }
        }

        cout << (N == 0 ? "YES" : "NO") << "\n";
    }

    return 0;
}
```