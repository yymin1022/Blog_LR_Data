[문제 바로가기](https://boj.kr/5596)

```c++
#include <bits/stdc++.h>

using namespace std;

int sum[2];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    for(int i = 0; i < 2; i++){
        for(int j = 0; j < 4; j++){
            int input;
            cin >> input;
            sum[i] += input;
        }
    }
    
    cout << max(sum[0], sum[1]) << "\n";
    
    return 0;
}
```