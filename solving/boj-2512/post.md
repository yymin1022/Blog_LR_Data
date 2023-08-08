[문제 바로가기](https://boj.kr/2512)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, money;
    cin >> N;

    vector<int> plan;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        plan.push_back(input);
    }

    cin >> money;
    sort(plan.begin(), plan.end());

    int ans = 0;
    int fromL = 0;
    int fromR = plan[N - 1];
    while(fromL <= fromR){
        int mid = (fromL + fromR) / 2;
        int tmp = 0;
        for(int i = 0; i < N; i++){
            tmp += min(plan[i], mid);
        }

        if(tmp <= money){
            ans = mid;
            fromL = mid + 1;
        }else{
            fromR = mid - 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```