[문제 바로가기](https://boj.kr/25418)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[1000001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int A, K;
    cin >> A >> K;

    queue<int> bfsQ;
    bfsQ.push(A);
    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        if(cur == K){
            cout << cnt[K] << "\n";
            return 0;
        }

        if(cur + 1 < 1000001 && cnt[cur + 1] == 0){
            bfsQ.push(cur + 1);
            cnt[cur + 1] = cnt[cur] + 1;
        }
        if(cur * 2 < 1000001 && cnt[cur * 2] == 0){
            bfsQ.push(cur * 2);
            cnt[cur * 2] = cnt[cur] + 1;
        }
    }

    return 0;
}
```