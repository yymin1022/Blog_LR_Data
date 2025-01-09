[문제 바로가기](https://boj.kr/31796)

```c++
#include <bits/stdc++.h>

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

    sort(arr.begin(), arr.end());

    int tmp = arr[0];
    int ans = 1;
    for(int i = 1; i < N; i++){
        if(arr[i] >= tmp * 2){
            tmp = arr[i];
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```
