[문제 바로가기](https://boj.kr/2660)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> arr[51];
    while(true){
        int A, B;
        cin >> A >> B;

        if(A == -1 && B == -1){
            break;
        }

        arr[A].push_back(B);
        arr[B].push_back(A);
    }

    int ans = 9999;
    vector<int> dist(51, 0);
    vector<int> score(51, 0);
    for(int i = 1; i <= N; i++){
        for(int j = 1; j <= N; j++){
            dist[j] = -1;
        }

        queue<int> bfsQ;
        bfsQ.push(i);
        dist[i] = 0;

        while(!bfsQ.empty()){
            int cur = bfsQ.front();
            bfsQ.pop();

            for(int j = 0; j < arr[cur].size(); j++){
                int next = arr[cur][j];

                if(dist[next] < 0){
                    bfsQ.push(next);
                    dist[next] = dist[cur] + 1;
                }
            }
        }

        int tmp = 0;
        for(int j = 1; j <= N; j++){
            tmp = max(dist[j], tmp);
        }

        ans = min(tmp, ans);
        score[i] = tmp;
    }

    vector<int> ansV;
    for(int i = 1; i <= N; i++){
        if(score[i] == ans){
            ansV.push_back(i);
        }
    }

    cout << ans << " ";
    cout << ansV.size() << "\n";

    for(int i = 0; i < ansV.size(); i++){
        cout << ansV[i] << " ";
    }

    return 0;
}
```