[문제 바로가기](https://boj.kr/2437)

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
    for(int i = 0; i < N; i++) {
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    if(arr[0] != 1){
        cout << 1 << "\n";
        return 0;
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(arr[i] > ans + 1){
            break;
        }

        ans += arr[i];
    }

    cout << ans + 1 << "\n";

    return 0;
}
```