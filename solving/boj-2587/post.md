[문제 바로가기](https://boj.kr/2587)

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
    vector<int> nums;

    for(int i = 0; i < 5; i++){
        int input;
        cin >> input;
        nums.push_back(input);
        sum += input;
    }

    sort(nums.begin(), nums.end());

    cout << sum / 5 << "\n" << nums[2];

    return 0;
}
```