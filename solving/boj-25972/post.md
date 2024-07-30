[문제 바로가기](https://boj.kr/25972)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr.push_back(make_pair(A, B));
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    int tmp = -1;
    for(int i = 0; i < N; i++){
        if(tmp < arr[i].first){
            ans++;
        }

        tmp = arr[i].first + arr[i].second;
    }

    cout << ans << "\n";

    return 0;
}
```