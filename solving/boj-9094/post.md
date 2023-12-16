[문제 바로가기](https://boj.kr/9094)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, M;
        cin >> N >> M;

        int ans = 0;
        for(int i = 1; i < N; i++){
            for(int j = i + 1; j < N; j++){
                if((i * i + j * j + M) % (i * j) == 0){
                    ans++;
                }
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```