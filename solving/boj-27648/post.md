[문제 바로가기](https://boj.kr/27648)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    if(N + M - 1 > K){
        cout << "NO" << "\n";
        return 0;
    }

    cout << "YES" << "\n";

    int num = 1;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cout << num << " ";
            num++;
        }

        num = i + 2;
        cout << "\n";
    }

    return 0;
}
```