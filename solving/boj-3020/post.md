[문제 바로가기](https://boj.kr/3020)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, H;
    cin >> N >> H;

    vector<int> bottom(N / 2);
    vector<int> top(N / 2);
    for(int i = 0; i < N; i += 2){
        int bottomI, topI;
        cin >> bottomI >> topI;
        bottom[i / 2] = bottomI;
        top[i / 2] = topI;
    }

    sort(bottom.begin(), bottom.end());
    sort(top.begin(), top.end());

    int minCnt = 0;
    int minVal = N;
    for(int i = 1; i <= H; i++){
        int cur = lower_bound(bottom.begin(), bottom.end(), i) - bottom.begin();
        cur += upper_bound(top.begin(), top.end(), H - i) - top.begin();
        cur = N - cur;

        if(cur < minVal){
            minCnt = 1;
            minVal = cur;
        }else if(cur == minVal){
            minCnt++;
        }
    }

    cout << minVal << " " << minCnt << "\n";

    return 0;
}```