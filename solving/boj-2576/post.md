[문제 바로가기](https://boj.kr/2576)

```c++
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int sum = 0;
    vector<int> odds;

    for(int i = 0; i < 7; i++){
        int input;
        cin >> input;

        if(input % 2){
            odds.push_back(input);
            sum += input;
        }
    }

    if(odds.size()){
        int min = *min_element(odds.begin(), odds.end());
        cout << sum << "\n" << min;
    }else{
        cout << -1;
    }

    return 0;
}```