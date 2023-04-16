[문제 바로가기](https://boj.kr/27940)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, K;
    cin >> N >> M >> K;

    int sum = 0;
    for(int i = 1; i <= M; i++){
        int t, r;
        cin >> t >> r;

        sum += r;

        if(sum > K){
            cout << i << " ";
            cout << 1 << "\n";
            return 0;
        }
    }

    cout << -1 << "\n";

    return 0;
}
```