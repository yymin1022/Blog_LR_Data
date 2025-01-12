[문제 바로가기](https://boj.kr/17520)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 2;
    for(int i = 2; i <= N; i++){
        if(i % 2 == 1){
            ans = (ans * 2) % 16769023;
        }
    }

    cout << ans << "\n";

    return 0;
}
```