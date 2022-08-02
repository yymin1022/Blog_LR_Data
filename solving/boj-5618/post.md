[문제 바로가기](https://boj.kr/5618)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
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

    for(int i = 1; i <= nums[N - 1]; i++){
        bool isOK = true;
        for(int j = 0; j < N; j++){
            if(nums[j] % i){
                isOK = false;
                break;
            }
        }

        if(isOK){
            cout << i << "\n";
        }
    }

    return 0;
}
```