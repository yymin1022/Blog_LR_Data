[문제 바로가기](https://boj.kr/5014)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int F, S, G, U, D;
    cin >> F >> S >> G >> U >> D;

    queue<int> bfsQ;
    vector<int> cnt(1000001, -1);
    bfsQ.push(S);
    cnt[S] = 0;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        if(cur == G){
            cout << cnt[cur] << "\n";
            return 0;
        }

        if(cur + U <= F && cnt[cur + U] < 0){
            bfsQ.push(cur + U);
            cnt[cur + U] = cnt[cur] + 1;
        }
        if(cur - D > 0 && cnt[cur - D] < 0){
            bfsQ.push(cur - D);
            cnt[cur - D] = cnt[cur] + 1;
        }
    }

    cout << "use the stairs" << "\n";

    return 0;
}
```