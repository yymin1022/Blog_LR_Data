[문제 바로가기](https://boj.kr/22857)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<int> arr;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        arr.push_back(input);
    }

    int ans = 0;
    int fromL = 0;
    int fromR = 0;
    int cnt = 0;
    int skipCnt = 0;
    while(fromR < N){
        if(skipCnt <= K){
            if(arr[fromR] % 2 == 0){
                cnt++;
                ans = max(cnt, ans);
            }else{
                skipCnt++;
            }
            fromR++;
        }else{
            if(arr[fromL] % 2 == 0){
                cnt--;
            }else{
                skipCnt--;
            }
            fromL++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```