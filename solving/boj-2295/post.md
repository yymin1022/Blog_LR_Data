[문제 바로가기](https://boj.kr/2295)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        nums.push_back(input);
    }

    vector<int> sums;
    for(int i = 0; i < N; i++){
        for(int j = i; j < N; j++){
            sums.push_back(nums[i] + nums[j]);
        }
    }

    sort(nums.begin(), nums.end());
    sort(sums.begin(), sums.end());

    for(int i = N - 1; i >= 0; i--){
        for(int j = 0; j < N; j++){
            if(binary_search(sums.begin(), sums.end(), nums[i] - nums[j])){
                cout << nums[i] << "\n";
                return 0;
            }
        }
    }

    return 0;
}```