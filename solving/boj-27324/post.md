[문제 바로가기](https://boj.kr/27324)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    if(N / 10 == N % 10){
        cout << 1 << "\n";
    }else{
        cout << 0 << "\n";
    }
    
    return 0;
}
```