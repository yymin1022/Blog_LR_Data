[문제 바로가기](https://boj.kr/17413)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string S;
    getline(cin, S);

    bool isReverse = true;
    stack<char> temp;
    for(int i = 0; i < S.size(); i++){
        if(S[i] == '<'){
            while(!temp.empty()){
                cout << temp.top();
                temp.pop();
            }

            cout << '<';
            isReverse = false;
            continue;
        }else if(S[i] == '>'){
            cout << '>';
            isReverse = true;
            continue;
        }

        if(isReverse){
            if(S[i] == ' '){
                while(!temp.empty()){
                    cout << temp.top();
                    temp.pop();
                }
                cout << ' ';
            }else{
                temp.push(S[i]);
            }
        }else{
            cout << S[i];
        }
    }

    while(!temp.empty()){
        cout << temp.top();
        temp.pop();
    }

    return 0;
}```