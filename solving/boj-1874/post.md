[문제 바로가기](https://boj.kr/1874)

```c++
#include <iostream>
#include <stack>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;

    stack<int> numStack;
    vector<char> historyVector;

    for(int i = 0, maxNum = 1; i < num; i++){
        int curNum;
        cin >> curNum;

        if(numStack.empty() || numStack.top() < curNum){
            while(maxNum <= curNum){
                numStack.push(maxNum);
                historyVector.push_back('+');
                maxNum++;
            }
        }else if(numStack.top() > curNum){
            break;
        }

        if(!numStack.empty() && numStack.top() == curNum){
            numStack.pop();
            historyVector.push_back('-');
        }
    }

    if(!numStack.empty()){
        cout << "NO\n";
    }else{
        for(int i = 0; i < historyVector.size(); i++){
            cout << historyVector[i] << "\n";
        }
    }

    return 0;
}
```