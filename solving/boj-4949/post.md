[문제 바로가기](https://boj.kr/4949)

```c++
#include <bits/stdc++.h>

using namespace std;
 
int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(0);

    string inputStr = "";

    while(1){
        getline(cin, inputStr);

        if(inputStr == "."){
            break;
        }

        bool isError = false;
        stack<char> stackStr;

        for(int i = 0; i < inputStr.length(); i++){
            if(inputStr[i] == '('){
                stackStr.push('(');
            }else if(inputStr[i] == '['){
                stackStr.push('[');
            }else if(inputStr[i] == ')'){
                if(stackStr.empty()){
                    isError = true;
                    break;
                }
                
                if(stackStr.top() == '('){
                    stackStr.pop();
                }else if(stackStr.top() == '['){
                    isError = true;
                    break;
                }
            }else if(inputStr[i] == ']'){
                if(stackStr.empty()){
                    isError = true;
                    break;
                }
                
                if(stackStr.top() == '['){
                    stackStr.pop();
                }else if(stackStr.top() == '('){
                    isError = true;
                    break;
                }
            }
        }

        if(!isError && stackStr.empty()){
            cout << "yes" << "\n";
        }else{
            cout << "no" << "\n";
        }
    }
}```