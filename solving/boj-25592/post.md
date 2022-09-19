[문제 바로가기](https://boj.kr/25592)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int cnt = 1;
    int sum = 0;
    while(sum <= N){
        sum += cnt;
        cnt++;
    }

    if(cnt % 2){
        cout << 0 << "\n";
    }else{
        cout << sum - N << "\n";
    }

    return 0;
}
```