[문제 바로가기](https://boj.kr/1781)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; ++i){
        int a, b;
        cin >> a >> b;
        arr.push_back(make_pair(a, b));
    }

    sort(arr.begin(), arr.end());

    int ans = 0;
    int idx = N - 1;
    priority_queue<int> pq;
    for(int i = N - 1; i >= 0; i--){
        while(idx >= 0 && arr[idx].first - 1 == i) {
            pq.push(arr[idx].second);
            idx--;
        }

        if(!pq.empty()){
            ans += pq.top();
            pq.pop();
        }
    }

    cout << ans << "\n";

    return 0;
}
```