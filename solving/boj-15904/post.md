[문제 바로가기](https://boj.kr/15904)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    string S;
    getline(cin, S);

    int idx = 0;
    string tmp = "";
    string UCPC = "UCPC";
    for(int i = 0; i < S.size(); i++){
        if(S[i] == UCPC[idx]){
            idx++;
            tmp += S[i];

            idx %= 4;
        }

        if(tmp == UCPC){
            cout << "I love UCPC" << "\n";
            return 0;
        }
    }

    cout << "I hate UCPC" << "\n";
    
    return 0;
}
```