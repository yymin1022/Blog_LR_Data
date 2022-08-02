[문제 바로가기](https://boj.kr/1037)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(void){
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

    sort(nums.begin(), nums.end());

    if(N == 1){
        cout << nums[0] * nums[0] << "\n";
    }else{
        cout << nums[0] * nums[N - 1] << "\n";
    }

	return 0;
}```