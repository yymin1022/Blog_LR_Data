[문제 바로가기](https://boj.kr/26122)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int K;
    string S;
    cin >> K >> S;

    int ans = 0;
    int cntN = 0;
    int cntS = 0;
    for(int i = 0; i < K; i++){
        if(cntN > 0 && cntS > 0 && S[i] != S[i - 1]){
            ans = max(min(cntN, cntS) * 2, ans);

            if(S[i] == 'N'){
                cntN = 0;
            }else{
                cntS = 0;
            }
        }

        if(S[i] == 'N'){
            cntN++;
        }else{
            cntS++;
        }
    }

    ans = max(min(cntN, cntS) * 2, ans);

    cout << ans << "\n";

    return 0;
}
```