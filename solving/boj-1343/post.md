[문제 바로가기](https://boj.kr/1343)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    string res = "";

    int cnt = 0;
    for(int i = 0; i < S.size(); i++){
        if(S[i] != 'X') {
            if(cnt % 2 != 0){
                cout << -1;
                return 0;
            }

            for(int j = 0; j < cnt / 4; j++){
                res += "AAAA";1
            }

            if(cnt % 4 == 2){
                res += "BB";
            }

            res.push_back('.');
            cnt = 0;
        }else{
            cnt++;
        }
    }

    if(cnt % 2 != 0){
        cout << -1 << "\n";
        return 0;
    }

    for(int j = 0; j < cnt / 4; j++){
        res += "AAAA";
    }
    if(cnt % 4 == 2){
        res += "BB";
    }

    cout << res << "\n";

    return 0;
}
```