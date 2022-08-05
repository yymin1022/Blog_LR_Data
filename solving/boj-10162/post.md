[문제 바로가기](https://boj.kr/10162)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int T;
    cin >> T;

    int ans[3];
    int button[3] = {300, 60, 10};
    for(int i = 0; i < 3; i++){
        int cnt = 0;
        while(T >= button[i]){
            cnt += T / button[i];
            T %= button[i];
        }

        ans[i] = cnt;
    }

    if(!T){
        for(int i = 0; i < 3; i++){
            cout << ans[i] << " ";
        }
    }else{
        cout << -1 << " ";
    }

    return 0;
}
```