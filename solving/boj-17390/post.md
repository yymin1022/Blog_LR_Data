[문제 바로가기](https://boj.kr/17390)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, Q;
    cin >> N >> Q;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    sort(arr.begin(), arr.end());

    for(int i = 1; i < N; i++){
        arr[i] += arr[i - 1];
    }

    while(Q--){
        int L, R;
        cin >> L >> R;
        cout << arr[R - 1] - (L - 2 < 0 ? 0 : arr[L - 2]) << "\n";
    }

    return 0;
}
```