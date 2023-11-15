[문제 바로가기](https://boj.kr/13904)

```c++
#include  <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    return A.second > B.second;
}

bool isSubj[1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> subj;
    for(int i = 0; i < N; i++){
        int D, W;
        cin >> D >> W;
        subj.push_back(make_pair(D, W));
    }

    sort(subj.begin(), subj.end(), cmp);

    int ans = 0;
    for(int i = 0; i < N; i++){
        int curD = subj[i].first;
        int curW = subj[i].second;

        for(int j = curD; j > 0; j--){
            if(!isSubj[j]){
                isSubj[j] = true;
                ans += curW;
                break;
            }
        }
    }

    cout << ans << "\n";

    return 0;
}
```