[문제 바로가기](https://boj.kr/1487)

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

    int maxCost = 0;
    int maxMargin = 0;
    for(int i = 0; i < N; i++){
        int sum = 0;
        for(int j = i; j < N; j++) {
            int cur = arr[i].first - arr[j].second;
            if(cur > 0){
                sum += cur;
            }
        }

        if(maxMargin < sum) {
            maxCost = arr[i].first;
            maxMargin = sum;
        }
    }

    cout << maxCost << "\n";

    return 0;
}
```