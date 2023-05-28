[문제 바로가기](https://boj.kr/2531)

```c++
#include <bits/stdc++.h>

using namespace std;

int tmp[30001];
int sushi[30001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, D, K, C;
    cin >> N >> D >> K >> C;

    for(int i = 0; i < N; i++){
        cin >> sushi[i];
    }

    int cnt = 0;
    for(int i = 0; i < K; i++){
        tmp[sushi[i]]++;
        if(tmp[sushi[i]] == 1){
            cnt++;
        }
    }

    tmp[C]++;
    if(tmp[C] == 1){
        cnt++;
    }

    int ans = 0;
    int left = 0;
    int right = K - 1;
    while(left < N){
        ans = max(cnt, ans);

        tmp[sushi[left]]--;
        if(tmp[sushi[left]] == 0){
            cnt--;
        }
        left++;

        right = (right + 1) % N;
        tmp[sushi[right]]++;
        if(tmp[sushi[right]] == 1){
            cnt++;
        }
    }

    cout << ans << "\n";

    return 0;
}
```