[문제 바로가기](https://boj.kr/30018)

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
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        ans += (arr[i] - input > 0 ? arr[i] - input : 0);
    }

    cout << ans << "\n";

    return 0;
}
```
