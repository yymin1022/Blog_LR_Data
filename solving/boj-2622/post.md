[문제 바로가기](https://boj.kr/2622)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int ans = 0;
    for(int i = 1; i < N; i++){
        for(int j = i; j < N; j++){
            int k = N - i - j;
            if(j > k){
                break;
            }
            if(i + j > k){
                ans++;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```