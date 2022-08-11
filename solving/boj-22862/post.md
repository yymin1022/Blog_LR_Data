[문제 바로가기](https://boj.kr/22862)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    vector<bool> isEven;
    vector<int> S;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        S.push_back(input);
        isEven.push_back(!(input % 2));
    }

    int ans = 0;
    int cnt = 0;
    int left = 0;
    int right = 0;
    while(right < N){
        if(cnt < K){
            if(!isEven[right]){
                cnt++;
            }

            right++;
            ans = max(right - left - cnt, ans);
        }else if(cnt == K && isEven[right]){
            right++;
            ans = max(right - left - cnt, ans);
        }else if(cnt == K && !isEven[right]){
            if(!isEven[left]){
                cnt--;
            }

            left++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```