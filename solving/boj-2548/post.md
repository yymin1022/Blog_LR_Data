[문제 바로가기](https://boj.kr/2548)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> nums(20000);
    for(int i = 0; i < N; i++){
        cin >> nums[i];
    }

    sort(nums.begin(), nums.begin() + N);

    if(N % 2){
        cout << nums[N / 2] << "\n";
    }else{
        cout << nums[N / 2 - 1] << "\n";
    }
}```