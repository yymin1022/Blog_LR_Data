[문제 바로가기](https://boj.kr/10799)

```c++
#include <iostream>
#include <stack>
#include <string>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int result = 0;
    stack<int> sticks;
    string input;

    cin >> input;

    for(int i = 0; i < input.size(); i++){
        if(input[i] == '('){
            sticks.push(0);
        }else{
            if(input[i - 1] == '('){
                result += sticks.size() - 1;
            }else{
                result += 1;
            }
            sticks.pop();
        }
    }

    cout << result;

    return 0;
}```