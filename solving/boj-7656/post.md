[문제 바로가기](https://boj.kr/7656)

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
    for(int i = 0; i < S.size(); i++){
        if(S[i] == '.' || S[i] == '?'){
            for(int j = idx; j < i; j++){
                if(S[j] - 'A'  >= 0 && S[j] - 'A' < 26){
                    idx = j;
                    break;
                }
            }

            string tmp = S.substr(idx, i - idx + 1);

            if(tmp[tmp.size() - 1] == '?'){
                cout << "Forty-two" << tmp.substr(4, tmp.size() - 5) << "." << "\n";
            }

            idx = i + 1;

        }
    }
    
    return 0;
}
```