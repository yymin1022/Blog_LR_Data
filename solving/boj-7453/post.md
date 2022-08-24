[문제 바로가기](https://boj.kr/7453)

```c++
#include <bits/stdc++.h>

using namespace std;

int nums[4001][4];
vector<int> sum1;
vector<int> sum2;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < 4; j++){
            cin >> nums[i][j];
        }
    }

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            sum1.push_back(nums[i][0] + nums[j][1]);
            sum2.push_back(nums[i][2] + nums[j][3]);
        }
    }

    sort(sum1.begin(), sum1.end());
    sort(sum2.begin(), sum2.end());

    long long ans = 0;
    int idx = 0;
    while(idx < N * N){
        int cur = sum1[idx];

        long long left = lower_bound(sum2.begin(), sum2.end(), cur * -1) - sum2.begin();
        long long right = upper_bound(sum2.begin(), sum2.end(), cur * -1) - sum2.begin();

        if(sum2[left] == cur * -1){
            ans += right - left;
        }

        idx++;
    }

    cout << ans << "\n";

    return 0;
}
```