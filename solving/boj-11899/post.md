[문제 바로가기](https://boj.kr/11899)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    cin >> S;

    int ans = 0;
    stack<char> stk;
    for(int i = 0; i < S.size(); i++){
        if(S[i] == '('){
            stk.push(S[i]);
        }else if(!stk.empty()){
            stk.pop();
        }else{
            ans++;
        }
    }

    ans += stk.size();

    cout << ans << "\n";

    return 0;
}

```