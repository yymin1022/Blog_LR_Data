[문제 바로가기](https://boj.kr/2491)

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

    int ans = 1;
    int lenAsc = 1;
    int lenDsc = 1;
    for(int i = 1; i < N; i++){
        if(arr[i] >= arr[i - 1]){
            lenAsc++;
        }else{
            lenAsc = 1;
        }

        if(arr[i] <= arr[i - 1]){
            lenDsc++;
        }else{
            lenDsc = 1;
        }

        ans = max(max(lenAsc, lenDsc), ans);
    }

    cout << ans << "\n";

    return 0;
}
```