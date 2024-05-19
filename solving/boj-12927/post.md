[문제 바로가기](https://boj.kr/12927)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int ans = 0;
    for(int i = 0; i < S.size(); i++){
        if(S[i] == 'Y'){
            for(int j = i; j < S.size(); j += i + 1){
                if(S[j] == 'Y'){
                    S[j] = 'N';
                }else{
                    S[j] = 'Y';
                }
            }
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```