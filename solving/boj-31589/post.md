[문제 바로가기](https://boj.kr/31589)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<long long> arr;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    long long ans = arr[N - 1];
    int cnt = K - 1;
    int left = 0;
    int right = N - 2;
    while(cnt > 1){
        ans += arr[right] - arr[left];
        cnt -= 2;
        left++;
        right--;
    }

    cout << ans << "\n";

    return 0;
}
```
