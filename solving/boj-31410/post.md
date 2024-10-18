[문제 바로가기](https://boj.kr/31410)

```c++
#include <bits/stdc++.h>

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

    vector<pair<int, int>> arr;
    for(int i = 0; i < N; i++){
        int x, p;
        cin >> x >> p;
        arr.push_back(make_pair(x, p));
    }

    sort(arr.begin(), arr.end(), cmp);

    long long startL = arr[0].first;
    long long startR = arr[N - 1].first;
    long long sumL = 0;
    long long sumR = 0;
    for(int i = 0; i < N; i++){
        sumL += arr[i].first - startL + arr[i].second;
        sumR += startR - arr[i].first + arr[i].second;
    }

    long long ans = 98765432100000000;
    for(int i = 0; i < N; i++){
        if(i > 0){
            ans = min(sumL - (arr[i].first - startL) - arr[i].second, ans);
        }
        if(i < N - 1){
            ans = min(sumR - (startR - arr[i].first) - arr[i].second, ans);
        }
    }

    ans = min(sumL - (N - 1) * (arr[1].first - startL) - arr[0].second, ans);
    ans = min(sumL - (startR - startL) - arr[N - 1].second, ans);
    ans = min(sumR - (N - 1) * (startR - arr[N - 2].first) - arr[N - 1].second, ans);
    ans = min(sumR - (startR - startL) - arr[0].second, ans);

    cout << ans << "\n";

    return 0;
}
```
