[문제 바로가기](https://boj.kr/2752)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<int> nums(3);
    cin >> nums[0];
    cin >> nums[1];
    cin >> nums[2];

    sort(nums.begin(), nums.end());

    cout << nums[0] << " " << nums[1] << " " << nums[2] << "\n";
    
    return 0;
}```