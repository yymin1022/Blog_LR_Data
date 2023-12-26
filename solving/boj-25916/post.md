[문제 바로가기](https://boj.kr/25916)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int left = 0;
    int right = 0;
    int sum = 0;
    while(right < N){
        if(sum + arr[right] <= M){
            sum += arr[right];
            ans = max(sum, ans);
            right++;
        }else{
            sum -= arr[left];
            left++;
        }

        if(left > right){
            sum += arr[right];
            right++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```