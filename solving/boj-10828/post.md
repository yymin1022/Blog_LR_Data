[문제 바로가기](https://boj.kr/10828)

```c++
#include <iostream>
#include <stack>
#include <string>

using namespace std;

int main(){
    int num;
    cin >> num;

    stack<int> numStack;

    for(int i = 0; i < num; i++){
        string command;
        cin >> command;

        if(command == "push"){
            int input;
            cin >> input;

            numStack.push(input);
        }else if(command == "pop"){
            if(!numStack.empty()){
                cout << numStack.top() << endl;
                numStack.pop();
            }else{
                cout << -1 << endl;
            }
        }else if(command == "size"){
            cout << numStack.size() << endl;
        }else if(command == "empty"){
            cout << (int)numStack.empty() << endl;
        }else if(command == "top"){
            if(!numStack.empty()){
                cout << numStack.top() << endl;
            }else{
                cout << -1 << endl;
            }
        }
    }

    return 0;
}
```