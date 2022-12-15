[문제 바로가기](https://boj.kr/11656)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    string S;
    cin >> S;

    vector<string> postfix;
    for(int i = 0; i < S.size(); i++){
        postfix.push_back(S.substr(i, S.size() - i));
    }

    sort(postfix.begin(), postfix.end());

    for(int i = 0; i < postfix.size(); i++){
        cout << postfix[i] << "\n";
    }
    
    return 0;
}
```