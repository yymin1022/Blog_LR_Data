[문제 바로가기](https://boj.kr/20922)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[100001];
int num[200001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    for(int i = 0; i < N; i++){
        cin >> num[i];
    }

    int ans = 0;
    int left = 0;
    int right = 0;
    while(left <= right && right < N){
        if(cnt[num[right]] < K){
            cnt[num[right]]++;
            ans = max(right - left + 1, ans);
            right++;
        }else if(cnt[num[right]] == K){
            cnt[num[left]]--;
            left++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```