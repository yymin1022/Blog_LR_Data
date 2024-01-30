[문제 바로가기](https://boj.kr/2847)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    for(int i = N - 2; i >= 0; i--){
        if(arr[i] >= arr[i + 1]){
            ans += arr[i] - arr[i + 1] + 1;
            arr[i] = arr[i + 1] - 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```