[문제 바로가기](https://boj.kr/1253)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;

    vector<long long> nums(N);
    for(int i = 0; i < N; i++){
        cin >> nums[i];
    }

    sort(nums.begin(), nums.end());

    int cnt = 0;
    for(int i = 0; i < N; i++){
        int fromL = 0;
        int fromR = N - 1;
        while(fromL < fromR){
            if(fromL == i){
                fromL++;
                continue;
            }
            if(fromR == i){
                fromR--;
                continue;
            }

            long long sum = nums[fromL] + nums[fromR];

            if(sum > nums[i]){
                fromR--;
            }else if(sum < nums[i]){
                fromL++;
            }else{
                cnt++;
                break;
            }
        }
    }

    cout << cnt << "\n";

    return 0;
}```