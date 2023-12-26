[문제 바로가기](https://boj.kr/24509)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    if(A.second == B.second){
        return A.first < B.first;
    }
    return A.second > B.second;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> score[4];
    for(int i = 0; i < N; i++){
        int X, A, B, C, D;
        cin >> X >> A >> B >> C >> D;
        score[0].push_back(make_pair(X, A));
        score[1].push_back(make_pair(X, B));
        score[2].push_back(make_pair(X, C));
        score[3].push_back(make_pair(X, D));
    }

    sort(score[0].begin(), score[0].end(), cmp);
    sort(score[1].begin(), score[1].end(), cmp);
    sort(score[2].begin(), score[2].end(), cmp);
    sort(score[3].begin(), score[3].end(), cmp);

    map<int, bool> prize;
    for(int i = 0; i < 4; i++){
        for(int j = 0; j < N; j++){
            if(!prize[score[i][j].first]){
                cout << score[i][j].first << " ";
                prize[score[i][j].first] = true;
                break;
            }
        }
    }

    return 0;
}
```