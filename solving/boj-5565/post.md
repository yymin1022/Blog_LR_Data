[문제 바로가기](https://boj.kr/5565)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    for(int i = 0; i < 9; i++){
        int input;
        cin >> input;
        N -= input;
    }

    cout << N << "\n";

    return 0;
}
```