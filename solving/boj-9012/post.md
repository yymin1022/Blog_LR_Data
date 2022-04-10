[문제 바로가기](https://boj.kr/9012)

```c++
#include <iostream>
#include <stack>
#include <string>

using namespace std;

int main(){
    int num;

    cin >> num;

    for(int i = 0; i < num; i++){
        int isErr = 0;
        string input;
        stack<int> msgStack;

        cin >> input;

        for(int j = 0; j < input.size(); j++){
            if(input[j] == '('){
                msgStack.push(1);
            }else{
                if(msgStack.empty()){
                    isErr = 1;
                    break;
                }else{
                    msgStack.pop();
                }
            }
        }

        if(!isErr && msgStack.empty()){
            cout << "YES\n";
        }else{
            cout << "NO\n";
        }
    }

    return 0;
}
```