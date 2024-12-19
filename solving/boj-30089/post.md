[문제 바로가기](https://boj.kr/30089)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        string S;
        cin >> S;

        int idx = 0;
        while(true){
            bool flag = true;
            for(int i = 0; i + idx < S.size(); i++){
                if(S[i + idx] != S[S.size() - i - 1]){
                    idx++;
                    flag = false;
                    break;
                }
            }

            if(flag){
                break;
            }
        }

        cout << S;
        for(int i = idx - 1; i >= 0; i--){
            cout << S[i];
        }
        cout << "\n";
    }

    return 0;
}
```
