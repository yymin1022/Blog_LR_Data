[문제 바로가기](https://boj.kr/1292)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    vector<int> nums;
    for(int i = 1; i <= 1000; i++){
        for(int j = 0; j < i; j++){
            nums.push_back(i);
        }

        if(nums.size() >= 1000){
            break;
        }
    }

    int A, B, sum = 0;
    cin >> A >> B;

    for(int i = A; i <= B; i++){
        sum += nums[i - 1];
    }

    cout << sum << "\n";

    return 0;
}
```