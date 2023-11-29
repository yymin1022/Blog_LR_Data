[문제 바로가기](https://boj.kr/1477)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M, L;
    cin >> N >> M >> L;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    arr.push_back(0);
    arr.push_back(L);
    sort(arr.begin(), arr.end());

    int ans = 987654321;
    int fromL = 1;
    int fromR = L - 1;
    while(fromL <= fromR){
        int mid = (fromL + fromR) / 2;
        int cnt = 0;

        for(int i = 1; i <= arr.size(); i++){
            int len = arr[i] - arr[i - 1];
            int tmp = len / mid;
            if(tmp > 0){
                cnt += tmp;
                if(len % mid == 0){
                    cnt--;
                }
            }
        }

        if(cnt > M){
            fromL = mid + 1;
        }else{
            fromR = mid - 1;
            ans = min(mid, ans);
        }
    }

    cout << ans << "\n";

    return 0;
}
```
