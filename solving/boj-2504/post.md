[문제 바로가기](https://boj.kr/2504)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    stack<char> strData;
    string input;

    cin >> input;
    
    int result = 0;
    int temp = 1;
    for(int i = 0; i < input.length(); i++){
        if(input[i] == '('){
            temp *= 2;
            strData.push('(');
        }else if(input[i] == '['){
            temp *= 3;
            strData.push('[');
        }else if(input[i] == ')' && (strData.empty() || strData.top() != '(')){
            result = 0;
            break;
        }else if(input[i] == ']' && (strData.empty() || strData.top() != '[')){
            result = 0;
            break;
        }else if(input[i] == ')'){
            if(input[i - 1] == '('){
                result += temp;
            }
            strData.pop();
            temp /= 2;
        }else if(input[i] == ']'){
            if(input[i - 1] == '['){
                result += temp;
            }
            strData.pop();
            temp /= 3;
        }
    }

    if(!strData.empty()){
        result = 0;
    }

    cout << result << "\n";
}```