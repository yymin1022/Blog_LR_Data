[문제 바로가기](https://boj.kr/1806)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, S;
    cin >> N >> S;

    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        nums.push_back(input);
    }

    int left = 0;
    int right = 0;
    int answer = 100001;
    int sum = nums[0];
    while(left <= right && right <= N){
        if(sum >= S){
            answer = min(answer, right - left + 1);
            sum -= nums[left];
            left++;
        }else{
            right++;
            sum += nums[right];
        }
    }

    if(answer > N){
        answer = 0;
    }

    cout << answer << "\n";

    return 0;
}```