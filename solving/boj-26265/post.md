[문제 바로가기](https://boj.kr/26265)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<string, vector<string>> A, pair<string, vector<string>> B){
    return A < B;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, vector<string>> db;
    for(int i = 0; i < N; i++){
        string mento, mentee;
        cin >> mento >> mentee;

        db[mento].push_back(mentee);
    }

    vector<pair<string, vector<string>>> result;
    for(auto iter = db.begin(); iter != db.end(); iter++){
        sort(iter->second.begin(), iter->second.end(), greater<string>());
        result.push_back(make_pair(iter->first, iter->second));
    }

    sort(result.begin(), result.end(), cmp);

    for(int i = 0; i < result.size(); i++){
        for(int j = 0; j < result[i].second.size(); j++){
            cout << result[i].first << " ";
            cout << result[i].second[j] << "\n";
        }
    }

    return 0;
}
```