[문제 바로가기](https://boj.kr/10797)

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

    vector<int> cars;
    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        cars.push_back(input);
    }

    cout << count(cars.begin(), cars.end(), num);

    return 0;
}```