[문제 바로가기](https://boj.kr/27446)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    map<int, bool> page;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        page[input] = true;
    }

    vector<int> arr;
    for(int i = 1; i <= N; i++){
        if(!page[i]){
            arr.push_back(i);
        }
    }

    int ans = 0;
    int prev = 0;
    for(int i = 0; i < arr.size(); i++){
        ans += (prev != 0 ? min((arr[i] - prev) * 2, 7) : 7);
        prev = arr[i];
    }

    cout << ans << "\n";

    return 0;
}
```
