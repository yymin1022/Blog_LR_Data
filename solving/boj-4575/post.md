[문제 바로가기](https://boj.kr/4575)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    string S;
    getline(cin, S);

    while(S != "END"){
        bool flag = true;
        vector<bool> arr(26, false);
        for(int i = 0; i < S.size(); i++){
            if(S[i] != ' '){
                if(arr[S[i] - 'A']){
                    flag = false;
                    break;
                }
                arr[S[i] - 'A'] = true;
            }
        }

        if(flag){
            cout << S << "\n";
        }

        getline(cin, S);
    }

    return 0;
}
```