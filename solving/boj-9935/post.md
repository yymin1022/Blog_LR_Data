[문제 바로가기](https://boj.kr/9935)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string bomb, word;
    cin >> word >> bomb;

    stack<char> stk;
    for(int i = 0; i < word.size(); i++){
        stk.push(word[i]);

        if(stk.size() >= bomb.size()){
            string temp;
            for(int j = 0; j < bomb.size(); j++){
                temp += stk.top();
                stk.pop();
            }

            reverse(temp.begin(), temp.end());

            if(temp != bomb){
                for(int j = 0; j < temp.size(); j++){
                    stk.push(temp[j]);
                }
            }
        }
    }

    if(stk.empty()){
        cout << "FRULA" << "\n";
        return 0;
    }

    string ans;
    while(!stk.empty()){
        ans += stk.top();
        stk.pop();
    }

    reverse(ans.begin(), ans.end());

    cout << ans << "\n";

    return 0;
}
```