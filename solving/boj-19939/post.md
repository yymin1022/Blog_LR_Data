[문제 바로가기](https://boj.kr/19939)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    N -= K * (K + 1) / 2;

    if(N < 0){
        cout << -1 << "\n";
    }else{
        N %= K;
        cout << (N == 0 ? K - 1 : K) << "\n";
    }

    return 0;
}
```
