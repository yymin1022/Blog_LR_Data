[문제 바로가기](https://boj.kr/2003)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<long long> nums;
    for(int i = 0; i < N; i++){
        long long temp;
        cin >> temp;
        nums.push_back(temp);
    }

    int cnt = 0;
    int left = 0;
    int right = 0;
    int sum = 0;
    while(true){
        if (sum >= M){
            sum -= nums[left];
            left++;
        }else{
            if(right == N){
                break;
            }

            sum += nums[right];
            right++;
        }
        
        if(sum == M){
            cnt++;
        }
    }

    cout << cnt << "\n";

    return 0;
}```