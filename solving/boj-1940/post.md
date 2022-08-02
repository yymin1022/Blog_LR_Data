[문제 바로가기](https://boj.kr/1940)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> nums;
    for(int i = 0; i < N; i++){
        int temp;
        cin >> temp;
        nums.push_back(temp);
    }

    sort(nums.begin(), nums.end());

    int cnt = 0;
    int left = 0;
    int right = N - 1;
    while(left < right){
        int sum = nums[left] + nums[right];

        if(sum == M){
            cnt++;
            left++;
        }else if(sum < M){
            left++;
        }else{
            right--;
        }
    }

    cout << cnt << "\n";

    return 0;
}```