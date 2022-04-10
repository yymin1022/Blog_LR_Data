[문제 바로가기](https://boj.kr/1931)

```c++
#include <bits/stdc++.h>

using namespace std;

bool compare(pair<int, int> a, pair<int, int> b){
    if(a.second == b.second){
        return a.first < b.first;
    }else{
        return a.second < b.second;
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> meeting;
    for(int i = 0; i < N; i++){
        int from, to;
        cin >> from >> to;

        meeting.push_back(make_pair(from, to));
    }

    sort(meeting.begin(), meeting.end(), compare);

    int cnt = 0;
    int temp = 0;
    for(int i = 0; i < meeting.size(); i++){
        if(meeting[i].first >= temp){
            cnt++;
            temp = meeting[i].second;
        }
    }

    cout << cnt << "\n";

    return 0;
}
```