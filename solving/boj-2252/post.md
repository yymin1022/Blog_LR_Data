[문제 바로가기](https://boj.kr/2252)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> from(N + 1, 0);
    vector<vector<int>> graph(N + 1, vector<int>());
    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        from[B]++;
        graph[A].push_back(B);
    }

    queue<int> sortQ;
    for(int i = 1; i <= N; i++){
        if(!from[i]){
            sortQ.push(i);
        }
    }

    while(!sortQ.empty()){
        int cur = sortQ.front();
        sortQ.pop();

        cout << cur << " ";

        for(int i = 0; i < graph[cur].size(); i++){
            int next = graph[cur][i];
            from[next]--;

            if(!from[next]){
                sortQ.push(next);
            }
        }
    }

    return 0;
}
```