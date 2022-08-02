[문제 바로가기](https://boj.kr/3273)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, X;
    cin >> N;

    vector<int> nums;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        nums.push_back(input);
    }
    sort(nums.begin(), nums.end());

    cin >> X;

    int cnt = 0;
    int fromStart = 0;
    int fromEnd = N - 1;
    while(fromStart < fromEnd){
        int tempSum = nums[fromStart] + nums[fromEnd];
        if(tempSum < X){
            fromStart++;
        }else if(tempSum > X){
            fromEnd--;
        }else{
            cnt++;
            fromStart++;
        }
    }

    cout << cnt << "\n";
    
    return 0;
}```