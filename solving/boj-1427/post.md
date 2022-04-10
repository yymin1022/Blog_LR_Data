[문제 바로가기](https://boj.kr/1427)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> nums;
    while(N){
        nums.push_back(N % 10);
        N /= 10;
    }

    sort(nums.rbegin(), nums.rend());

    for(int i = 0; i < nums.size(); i++){
        cout << nums[i];
    }

    return 0;
}
```