[문제 바로가기](https://boj.kr/10986)

```c++
#include <bits/stdc++.h>

using namespace std;

long long cnt[1001];
long long sum[1000001];
 
int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    long long answer = 0;
    for(int i = 1; i <= N; i++){
        cin >> sum[i];
        sum[i] += sum[i - 1];
        sum[i] %= M;

        if(sum[i] == 0){
            answer++;
        }

        cnt[sum[i]]++;
    }

    for(int i = 0; i < M; i++){
        answer += cnt[i] * (cnt[i] - 1)/ 2;
    }

    cout << answer << "\n";

    return 0;
}```