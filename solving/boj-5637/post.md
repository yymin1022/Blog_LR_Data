[문제 바로가기](https://boj.kr/5637)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string ans;
    while(true){
        string S;
        cin >> S;

        if(S == "E-N-D"){
            break;
        }

        string tmp;
        for(int i = 0; i < S.size(); i++){
            if((S[i] >= 'a' && S[i] <= 'z') || S[i] == '-'){
                tmp += S[i];
            }else if(S[i] >= 'A' && S[i] <= 'Z'){
                tmp += S[i] - 'A' + 'a';
            }
        }

        if(tmp.size() > ans.size()){
            ans = tmp;
        }
    }

    cout << ans << "\n";

    return 0;
}
```