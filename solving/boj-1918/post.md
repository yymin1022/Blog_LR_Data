[문제 바로가기](https://boj.kr/1918)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string formula;
    cin >> formula;

    stack<char> symbol;
    for(int i = 0; i < formula.size(); i++){
        if(formula[i] == '+' || formula[i] == '-'){
            while(!symbol.empty() && symbol.top() != '('){
                cout << symbol.top();
                symbol.pop();
            }

            symbol.push(formula[i]);
        }else if(formula[i] == '*' || formula[i] == '/'){
            while(!symbol.empty() && (symbol.top() == '*' || symbol.top() == '/')){
                cout << symbol.top();
                symbol.pop();
            }

            symbol.push(formula[i]);
        }else if(formula[i] == '('){
            symbol.push(formula[i]);
        }else if(formula[i] == ')'){
            while(symbol.top() != '('){
                cout << symbol.top();
                symbol.pop();
            }

            symbol.pop();
        }else{
            cout << formula[i];
        }
    }

    while(!symbol.empty()){
        cout << symbol.top();
        symbol.pop();
    }

    return 0;
}
```