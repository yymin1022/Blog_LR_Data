[문제 바로가기](https://boj.kr/1912)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> dp;
    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        dp.push_back(input);
        nums.push_back(input);
    }

    for(int i = 0; i < N; i++){
        dp[i] = max(dp[i - 1] + nums[i], dp[i]);
    }

    cout << *max_element(dp.begin(), dp.end()) << "\n";

    return 0;
}```