[문제 바로가기](https://boj.kr/23559)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    return abs(A.first - A.second) > abs(B.first - B.second);
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, X;
    cin >> N >> X;

    int ans = 0;
    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr.push_back(make_pair(A, B));
        ans += B;
        X -= 1000;
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < N; i++){
        if(X >= 4000 && arr[i].first - arr[i].second >= 0){
            X -= 4000;
            ans += arr[i].first - arr[i].second;
        }
    }
    
    cout << ans << "\n";

    return 0;
}
```