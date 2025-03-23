[문제 바로가기](https://boj.kr/24446)

```c++
#include  <bits/stdc++.h>

using namespace std;

int visitCnt[100001];
vector<int> arr[100001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M, R;
    cin >> N >> M >> R;

    for(int i = 0; i < M; i++){
        int U, V;
        cin >> U >> V;
        arr[U].push_back(V);
        arr[V].push_back(U);
    }

    queue<int> bfsQ;
    bfsQ.push(R);
    visitCnt[R] = 1;

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 0; i < arr[cur].size(); i++){
            int next = arr[cur][i];

            if(visitCnt[next] == 0){
                bfsQ.push(next);
                visitCnt[next] = visitCnt[cur] + 1;
            }
        }
    }

    for(int i = 1; i <= N; i++){
        cout << (visitCnt[i] == 0 ? -1 : visitCnt[i] - 1) << "\n";
    }

    return 0;
}

```