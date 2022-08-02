[문제 바로가기](https://boj.kr/1935)

```c++
#include <iostream>
#include <stack>
#include <string>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int numCount;
    stack<double> numStack;
    string formula;
    vector<int> numbers;

    cin >> numCount >> formula;

    for(int i = 0; i < numCount; i++){
        int input;
        cin >> input;
        numbers.push_back(input);
    }

    for(int i = 0; i < formula.size(); i++){
        char curValue = formula[i];
        if((int)curValue > 64 && (int)curValue < 91){
            curValue = numbers[(65 - (int)curValue) * -1] + '0';
            numStack.push(curValue - '0');
        }else{
            double num1, num2;
            num1 = numStack.top();
            numStack.pop();
            num2 = numStack.top();
            numStack.pop();

            if(curValue == '+'){
                numStack.push(num2 + num1);
            }else if(curValue == '-'){
                numStack.push(num2 - num1);
            }else if(curValue == '*'){
                numStack.push(num2 * num1);
            }else if(curValue == '/'){
                numStack.push(num2 / num1);
            }
        }
    }

    cout << fixed;
    cout.precision(2);
    cout << numStack.top() << "\n";

    return 0;
}```