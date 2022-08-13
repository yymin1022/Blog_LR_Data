[문제 바로가기](https://boj.kr/12892)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    long long N, D;
    cin >> N >> D;

    vector<pair<long long, long long>> gift;
    for(int i = 0; i < N; i++){
        long long P, V;
        cin >> P >> V;
        gift.push_back(make_pair(P, V));
    }

    if(!N){
        cout << gift[0].second << "\n";
        return 0;
    }

    sort(gift.begin(), gift.end());

    long long ans = 0;
    long long happy = 0;
    int left = 0;
    int right = 0;
    while(left <= right && right < N){
        int diff = gift[right].first - gift[left].first;
        if(diff < D){
            happy += gift[right].second;
            ans = max(happy, ans);
            right++;
        }else{
            happy -= gift[left].second;
            left++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```