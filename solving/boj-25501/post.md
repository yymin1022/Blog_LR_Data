[문제 바로가기](https://boj.kr/25501)

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
        string S, tempS;
        cin >> S;

        tempS = S;
        reverse(tempS.begin(), tempS.end());

        bool isPal = true;
        int cnt = 1;
        for(int i = 0; i < S.size() / 2; i++){
            if(S[i] != tempS[i]){
                isPal = false;
                break;
            }

            cnt++;
        }

        cout << (int)isPal << " " << cnt << "\n";
    }

    return 0;
}
```