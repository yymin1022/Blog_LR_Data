[문제 바로가기](https://boj.kr/10282)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N, D, C;
        cin >> N >> D >> C;

        vector<int> isHacked(N + 1, -1);
        vector<pair<int, int>> dependency[10001];
        for(int i = 0; i < D; i++){
            int A, B, S;
            cin >> A >> B >> S;
            dependency[B].push_back(make_pair(S, A));
        }

        priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>>> bfsQ;
        bfsQ.push(make_pair(0, C));
        isHacked[C] = 0;
        while(!bfsQ.empty()){
            int curPC = bfsQ.top().second;
            int curTime = bfsQ.top().first;
            bfsQ.pop();

            if(isHacked[curPC] != -1 && isHacked[curPC] < curTime){
                continue;
            }

            for(int i = 0; i < dependency[curPC].size(); i++){
                int nextPC = dependency[curPC][i].second;
                int nextTime = curTime + dependency[curPC][i].first;

                if(isHacked[nextPC] == -1 || nextTime < isHacked[nextPC]){
                    isHacked[nextPC] = nextTime;
                    bfsQ.push(make_pair(nextTime, nextPC));
                }
            }
        }

        int ansCnt = 0;
        int ansTime = 0;
        for(int i = 1; i <= N; i++){
            if(isHacked[i] != -1){
                ansCnt++;
                ansTime = max(isHacked[i], ansTime);
            }
        }

        cout << ansCnt << " ";
        cout << ansTime << "\n";
    }

    return 0;
}

```
