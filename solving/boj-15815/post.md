[문제 바로가기](https://boj.kr/15815)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string input;
    getline(cin, input);

    stack<int> stk;
    for(int i = 0; i < input.length(); i++){
        char c = input[i];

        if(c >= '0' && c <= '9'){
            stk.push(c - '0');
        }else{
            int A = stk.top();
            stk.pop();
            int B = stk.top();
            stk.pop();

            if(c == '+'){
                stk.push(B + A);
            }else if(c == '-'){
                stk.push(B - A);
            }else if(c == '*'){
                stk.push(B * A);
            }else if(c == '/'){
                stk.push(B / A);
            }
        }
    }

    cout << stk.top();

    return 0;
}
```