[문제 바로가기](https://boj.kr/30454)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, L;
    cin >> N >> L;

    int ans[2] = {0, 0};
    for(int i = 0; i < N; i++){
        string S;
        cin >> S;

        int cnt = 0;
        for(int j = 0; j < L; j++){
            if((j == 0 && S[j] == '1') || (j > 0 && S[j] == '1' && S[j - 1] == '0')){
                cnt++;
            }
        }

        if(ans[0] < cnt){
            ans[0] = cnt;
            ans[1] = 1;
        }else if(ans[0] == cnt){
            ans[1]++;
        }
    }

    cout << ans[0] << " ";
    cout << ans[1] << "\n";

    return 0;
}
```
