[문제 바로가기](https://boj.kr/6118)

```c++
#include <bits/stdc++.h>

using namespace std;

int visitCnt[20001];
vector<int> arr[20001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;
    N++;

    for(int i = 0; i < M; i++){
        int A, B;
        cin >> A >> B;
        arr[A].push_back(B);
        arr[B].push_back(A);
    }

    queue<int> bfsQ;
    bfsQ.push(1);
    visitCnt[1] = 0;

    for(int i = 2; i < N; i++){
        visitCnt[i] = 20001;
    }

    while(!bfsQ.empty()){
        int cur = bfsQ.front();
        bfsQ.pop();

        for(int i = 0; i < arr[cur].size(); i++){
            int next = arr[cur][i];

            if(visitCnt[cur] + 1 < visitCnt[next]){
                bfsQ.push(next);
                visitCnt[next] = visitCnt[cur] + 1;
            }
        }
    }

    int ansVal = max_element(visitCnt, visitCnt + N) - visitCnt;
    cout << ansVal << " ";
    cout << visitCnt[ansVal] << " ";
    cout << count(visitCnt, visitCnt + N, visitCnt[ansVal]) << "\n";

    return 0;
}

```