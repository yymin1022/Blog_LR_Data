[문제 바로가기](https://boj.kr/9020)

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
    
    int T;
    cin >> T;
    for(int i = 0; i < T; i++){
        int n;
        cin >> n;

        for(int j = n / 2; j >= 2; j--){
            if(nums[j] && nums[n - j]){
                cout << j << " " << n - j << "\n";
                break;
            }
        }
    }

    return 0;
}
```