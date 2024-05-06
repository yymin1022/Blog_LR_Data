[문제 바로가기](https://boj.kr/16162)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, A, D;
    cin >> N >> A >> D;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(arr[i] == A + (D * ans)){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```