[문제 바로가기](https://boj.kr/28353)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    int fromL = 0;
    int fromR = N - 1;
    while(fromL < fromR){
        int sum = arr[fromL] + arr[fromR];

        if(sum > K){
            fromR--;
        }else{
            ans++;
            fromL++;
            fromR--;
        }
    }

    cout << ans << "\n";

    return 0;
}
```