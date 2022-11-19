[문제 바로가기](https://boj.kr/25377)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    bool isBought = false;
    int ans = 987654321;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;

        if(A <= B){
            ans = min(B, ans);
            isBought = true;
        }
    }

    if(isBought){
        cout << ans << "\n";
    }else{
        cout << -1 << "\n";
    }

    return 0;
}
```