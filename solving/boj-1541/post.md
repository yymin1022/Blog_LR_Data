[문제 바로가기](https://boj.kr/1541)

```c++
#include <bits/stdc++.h>

using namespace std;

int getNumber(vector<int>);

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string input;
    cin >> input;
    
    int flag = 1;
    int result = 0;
    vector<int> tempNum;
    for(int i = 0; i < input.size(); i++){
        if(input[i] == '-'){
            result += flag * getNumber(tempNum);
            tempNum.clear();
            flag = -1;
        }else if(input[i] == '+'){
            result += flag * getNumber(tempNum);
            tempNum.clear();
        }else{
            tempNum.push_back(input[i] - '0');
        }
    }

    result += flag * getNumber(tempNum);

    cout << result << "\n";

    return 0;
}

int getNumber(vector<int> temp){
    int result = 0;
    for(int i = 0; i < temp.size(); i++){
        result += temp[i] * pow(10, temp.size() - i - 1);
    }

    return result;
}
```