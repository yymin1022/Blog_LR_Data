[문제 바로가기](https://boj.kr/3079)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<unsigned long long> T;
    for(int i = 0; i < N; i++){
        unsigned long long input;
        cin >> input;
        T.push_back(input);
    }

    sort(T.begin(), T.end());

    unsigned long long ans = ULONG_LONG_MAX;
    unsigned long long left = 1;
    unsigned long long right = T[N - 1] * M;
    while(left <= right){
        unsigned long long mid = (left + right) / 2;
        unsigned long long sum = 0;

        for(int i = 0; i < N; i++){
            sum += mid / T[i];
        }

        if(sum < M){
            left = mid + 1;
        }else{
            ans = min(mid, ans);
            right = mid - 1;
        }
    }

    cout << ans << "\n";

    return 0;
}
```