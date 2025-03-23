[문제 바로가기](https://boj.kr/5237)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isVisit[101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int N, K;
        cin >> N >> K;

        memset(isVisit, false, sizeof(isVisit));
        vector<int> arr[101];
        for(int i = 0; i < K; i++){
            int A, B;
            cin >> A >> B;
            arr[A].push_back(B);
            arr[B].push_back(A);
        }

        queue<int> bfsQ;
        bfsQ.push(0);
        isVisit[0] = true;

        while(!bfsQ.empty()){
            int cur = bfsQ.front();
            bfsQ.pop();

            for(int i = 0; i < arr[cur].size(); i++){
                int next = arr[cur][i];
                if(!isVisit[next]){
                    bfsQ.push(next);
                    isVisit[next] = true;
                }
            }
        }

        int isConnected = true;
        for(int i = 0; i < N; i++){
            if(!isVisit[i]){
                isConnected = false;
                break;
            }
        }

        cout << (isConnected ? "Connected." : "Not connected.") << "\n";
    }

    return 0;
}
```