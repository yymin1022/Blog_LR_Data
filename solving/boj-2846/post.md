[문제 바로가기](https://boj.kr/2846)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
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
    int start = 0;
    int end = 0;
    for(int i = 1; i < N; i++){
        if(arr[i] > arr[i - 1]){
            end++;
            ans = max(arr[end] - arr[start], ans);
        }else{
            start = i;
            end = i;
        }
    }

    cout << ans << "\n";
    
    return 0;
}
```