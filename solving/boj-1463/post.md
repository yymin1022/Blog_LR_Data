[문제 바로가기](https://boj.kr/1463)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;
 
    vector<int> nums;
    nums.push_back(0);
    nums.push_back(0);
    for(int i = 2; i <= N; i++){
        nums.push_back(nums[i - 1] + 1);
 
        if(i % 2 == 0){
            int temp = nums[i / 2] + 1;
            if(temp < nums[i]){
                nums[i] = temp;
            }
        }

        if(i % 3 == 0){
            int temp = nums[i / 3] + 1;
            if(temp < nums[i]){
                nums[i] = temp;
            }
        }
    }
 
    cout << nums[N] << "\n";

    return 0;
}
```