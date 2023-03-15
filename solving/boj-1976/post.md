[문제 바로가기](https://boj.kr/1976)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[201];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> route[201];
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            int input;
            cin >> input;
            if(input){
                route[i].push_back(j);
            }
        }
    }

    vector<int> plan;
    for(int i = 0; i < M; i++){
        int input;
        cin >> input;
        plan.push_back(input);
    }

    queue<int> bfsQ;
    bfsQ.push(plan[0]);
    isVisit[plan[0]] = true;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 0; i < route[cur].size(); i++){
            int next = route[cur][i];

            if(!isVisit[next]){
                bfsQ.push(next);
                isVisit[next] = true;
            }
        }
    }

    for(int i = 0; i < M; i++){
        if(!isVisit[plan[i]]){
            cout << "NO" << "\n";
            return 0;
        }
    }

    cout << "YES" << "\n";

    return 0;
}
```