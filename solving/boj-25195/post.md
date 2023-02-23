[문제 바로가기](https://boj.kr/25195)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isFan[100001];
bool isVisit[100001];
vector<int> tour[100001];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < M; i++){
        int u, v;
        cin >> u >> v;
        tour[u].push_back(v);
    }

    int S;
    cin >> S;

    for(int i = 0; i < S; i++){
        int input;
        cin >> input;
        isFan[input] = true;
    }

    if(isFan[1]){
        cout << "Yes" << "\n";
        return 0;
    }

    queue<int> bfsQ;
    bfsQ.push(1);
    isVisit[1] = true;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        if(!isFan[cur] && tour[cur].empty()){
            cout << "yes" << "\n";
            return 0;
        }

        for(int i = 0; i < tour[cur].size(); i++){
            if(!isFan[tour[cur][i]] && !isVisit[tour[cur][i]]){
                bfsQ.push(tour[cur][i]);
                isVisit[tour[cur][i]] = true;
            }
        }
    }

    cout << "Yes" << "\n";

    return 0;
}
```