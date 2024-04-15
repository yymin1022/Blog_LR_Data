[문제 바로가기](https://boj.kr/14469)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    return A.first < B.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> cow;
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        cow.push_back(make_pair(A, B));
    }

    sort(cow.begin(), cow.end(), cmp);

    int ans = 0;
    int idx = 0;
    while(idx < N){
        int curStart = cow[idx].first;
        int curDuration = cow[idx].second;

        if(ans >= curStart){
            ans += curDuration;
            idx++;
        }else{
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```