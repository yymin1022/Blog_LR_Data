[문제 바로가기](https://boj.kr/15810)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    priority_queue<pair<long long, long long>, vector<pair<long long, long long>>, greater<pair<long long, long long>>> pq;
    for(int i = 0; i < N; i++){
        long long input;
        cin >> input;
        pq.push(make_pair(input, input));
    }

    for(int i = 0; i < M - 1; i++){
        long long A = pq.top().first;
        long long B = pq.top().second;
        pq.pop();
        pq.push(make_pair(A + B, B));
    }

    cout << pq.top().first << "\n";

    return 0;
}
```