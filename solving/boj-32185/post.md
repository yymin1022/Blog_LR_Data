[문제 바로가기](https://boj.kr/32185)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    return A.first > B.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int V, P, S;
    cin >> V >> P >> S;

    vector<pair<int, int>> arr;
    for(int i = 1; i <= N; i++){
        int v, p, s;
        cin >> v >> p >> s;

        if(v + p + s <= V + P + S){
            arr.push_back(make_pair(v + p + s, i));
        }
    }

    sort(arr.begin(), arr.end(), cmp);

    vector<int> ans;
    ans.push_back(0);
    for(int i = 0; i < arr.size(); i++){
        if(ans.size() < M){
            ans.push_back(arr[i].second);
        }else{
            break;
        }
    }

    for(int i = 0; i < ans.size(); i++){
        cout << ans[i] << " ";
    }

    return 0;
}

```
