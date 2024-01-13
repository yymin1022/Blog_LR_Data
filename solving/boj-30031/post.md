[문제 바로가기](https://boj.kr/30031)

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
    for(int i = 0; i < N; i++){
        int W, H;
        cin >> W >> H;

        if(W == 136){
            ans += 1000;
        }else if(W == 142){
            ans += 5000;
        }else if(W == 148){
            ans += 10000;
        }else{
            ans += 50000;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
