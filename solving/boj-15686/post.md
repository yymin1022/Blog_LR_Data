[문제 바로가기](https://boj.kr/15686)

```c++
#include  <bits/stdc++.h>

using namespace std;

void closeChick(int, int);

int N, M;
int ans = 987654321;
vector<pair<int, int>> chicken;
vector<pair<int, int>> home;
vector<int> chickIdx;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            int input;
            cin >> input;

            if(input == 1){
                home.push_back(make_pair(i, j));
            }else if(input == 2){
                chicken.push_back(make_pair(i, j));
            }
        }
    }

    closeChick(0, 0);

    cout << ans << "\n";

    return 0;
}

void closeChick(int idx, int cnt){
    if(idx > chicken.size()){
        return;
    }

    if(cnt == M){
        int sumDist = 0;

        for(int i = 0; i < home.size(); i++){
            int curDist = 987654321;

            for(int j = 0; j < chickIdx.size(); j++){
                curDist = min(abs(home[i].first - chicken[chickIdx[j]].first) + abs(home[i].second - chicken[chickIdx[j]].second), curDist);
            }

            sumDist += curDist;
        }

        ans = min(sumDist, ans);

        return;
    }

    chickIdx.push_back(idx);
    closeChick(idx + 1, cnt + 1);
    chickIdx.pop_back();
    closeChick(idx + 1, cnt);
}
```