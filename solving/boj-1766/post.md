[문제 바로가기](https://boj.kr/1766)

```c++
#include  <bits/stdc++.h>

using namespace std;

int indegree[32001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> ans;
    vector<int> problem[32001];
    priority_queue<int, vector<int>, greater<int>> pq;
    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        problem[A].push_back(B);
        indegree[B]++;
    }

    for(int i = 1; i <= N; i++){
        if(indegree[i] == 0){
            pq.push(i);
        }
    }

    while(!pq.empty()){
        int cur = pq.top();
        pq.pop();
        ans.push_back(cur);

        for(int i = 0; i < problem[cur].size(); i++){
            int next = problem[cur][i];
            indegree[next]--;
            if(indegree[next] == 0){
                pq.push(next);
            }
        }
    }

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}
```