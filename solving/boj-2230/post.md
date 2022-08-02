[문제 바로가기](https://boj.kr/2230)

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
        int input;
        cin >> input;
        nums.push_back(input);
    };

    sort(nums.begin(), nums.end());

    int fromL = 0;
    int fromR = 0;
    int minDiffer = 2000000000;
    while(fromL < N && fromR < N){
        int curDiffer = nums[fromR] - nums[fromL];

        if(curDiffer < M) {
            fromR++;
        }else{
            fromL++;
            minDiffer = min(curDiffer, minDiffer);
        }
    }

    cout << minDiffer << "\n";

    return 0;
}```