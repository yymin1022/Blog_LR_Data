[문제 바로가기](https://boj.kr/13913)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[100001];
int from[100001];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, K;
    cin >> N >> K;

    queue<int> bfsQ;
    bfsQ.push(N);
    isVisit[N] = true;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        if(cur == K){
            break;
        }

        if(cur - 1 >= 0 && !isVisit[cur - 1]){
            bfsQ.push(cur - 1);
            from[cur - 1] = cur;
            isVisit[cur - 1] = true;
        }

        if(cur + 1 <= 100000 && !isVisit[cur + 1]){
            bfsQ.push(cur + 1);
            from[cur + 1] = cur;
            isVisit[cur + 1] = true;
        }

        if(cur * 2 <= 100000 && !isVisit[cur * 2]){
            bfsQ.push(cur * 2);
            from[cur * 2] = cur;
            isVisit[cur * 2] = true;
        }
    }

    int next = K;
    vector<int> log;
    while(next != N){
        log.push_back(next);
        next = from[next];
    }
    log.push_back(N);

    cout << log.size() - 1 << "\n";
    for(int i = log.size() - 1; i >= 0; i--){
        cout << log[i] << " ";
    }

    return 0;
}
```