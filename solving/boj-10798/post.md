[문제 바로가기](https://boj.kr/10798)

```c++
#include <algorithm>
#include <iostream>
#include <string>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    vector<string> input;

    for(int i = 0; i < 5; i++){
        string inputStr;
        cin >> inputStr;
        input.push_back(inputStr);
    }

    for(int i = 0; i < 15; i++){
        for(int j = 0; j < 5; j++){
            if(input[j].size() > i){
                cout << input[j][i];
            }
        }
    }

    return 0;
}```