[문제 바로가기](https://boj.kr/2476)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int num;
    cin >> num;
    
    vector<int> money;

    for(int i = 0; i < num; i++){
        int isEnd = 0;
        int result;
        vector<int> dice;

        for(int j = 0; j < 3; j++){
            int input;
            cin >> input;
            dice.push_back(input);
        }

        for(int j = 0; j < 3; j++){
           if(count(dice.begin(), dice.end(), dice[j]) == 3){
               isEnd = 1;
               result = 10000 + dice[j] * 1000;
               break;
           }else if(count(dice.begin(), dice.end(), dice[j]) == 2){
               isEnd = 1;
               result = 1000 + dice[j] * 100;
               break;
           }
        }

        if(!isEnd){
            result = *max_element(dice.begin(), dice.end()) * 100;
        }

        money.push_back(result);
    }

    cout << *max_element(money.begin(), money.end());
}
```