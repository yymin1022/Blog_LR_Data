[문제 바로가기](https://boj.kr/2118)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    int sum = 0;
    vector<int> top;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        top.push_back(input);
        sum += input;
    }

    int ans = 0;
    int left = 0;
    int right = 1;
    int sum1 = top[0];
    int sum2 = sum - top[0];
    while(right < N){
        ans = max(min(sum1, sum2), ans);

        if(sum1 > sum2){
            sum1 -= top[left];
            sum2 += top[left];
            left++;
        }else{
            sum1 += top[right];
            sum2 -= top[right];
            right++;
            if(right > N){
                right -= N;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```