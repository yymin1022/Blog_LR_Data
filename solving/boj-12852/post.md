[문제 바로가기](https://boj.kr/12852)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N;
    cin >> N;
 
    vector<int> history;
    vector<int> nums;
    history.push_back(0);
    history.push_back(0);
    nums.push_back(0);
    nums.push_back(0);
    for(int i = 2; i <= N; i++){
        history.push_back(i - 1);
        nums.push_back(nums[i - 1] + 1);
 
        if(i % 2 == 0){
            int temp = nums[i / 2];
            if(temp < nums[i]){
                history[i] = i / 2;
                nums[i] = temp + 1;
            }
        }

        if(i % 3 == 0){
            int temp = nums[i / 3];
            if(temp < nums[i]){
                history[i] = i / 3;
                nums[i] = temp + 1;
            }
        }
    }
 
    cout << nums[N] << "\n";

    int num = N;
    while(true){
        cout << num << " ";
        num = history[num];

        if(!num){
            break;
        }
    }

    return 0;
}```