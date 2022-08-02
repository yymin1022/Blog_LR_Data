[문제 바로가기](https://boj.kr/4948)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<bool> nums(250000, true);
    nums[0] = nums[1] = false;
    for(int i = 2; i < 250000; i++){
        if(!nums[i]){
            continue;
        }
        for(int j = i * 2; j < 250000; j += i){
            nums[j] = false;
        }
    }

    vector<int> sum(250000, 0);
    for(int i = 2; i < 250000; i++){
        if(nums[i]){
            sum[i]++;
        }
        sum[i] += sum[i - 1];
    }

    int N;
    cin >> N;
    while(N){
        cout << sum[N * 2] - sum[N] << "\n";
        cin >> N;
    }

    return 0;
}```