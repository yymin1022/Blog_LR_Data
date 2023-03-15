[문제 바로가기](https://boj.kr/11549)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    int ans = 0;
    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        if(T == input){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```