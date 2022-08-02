[문제 바로가기](https://boj.kr/10211)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<int> nums(N + 1, 0);
        for(int i = 0; i < N; i++){
            cin >> nums[i];
            nums[i] += nums[i - 1];
        }

        int maxV = -1000000;
        for(int i = 1; i <= N; i++){
            for(int j = i - 1; j < N; j++){
                maxV = max(maxV, nums[j] - nums[j - i]);
            }
        }

        cout << maxV << "\n";
    }

    return 0;
}```