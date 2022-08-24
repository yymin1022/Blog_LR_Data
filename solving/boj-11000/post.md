[문제 바로가기](https://boj.kr/11000)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> lecture;
    for(int i = 0; i < N; i++){
        int
        S, T;
        cin >> S >> T;
        lecture.push_back(make_pair(S, T));
    }

    sort(lecture.begin(), lecture.end());

    priority_queue<int, vector<int>, greater<int>> pq;
    pq.push(lecture[0].second);
    for(int i = 1; i < N; i++){
        if(pq.top() <= lecture[i].first){
            pq.pop();
        }
        pq.push(lecture[i].second);
    }

    cout << pq.size() << "\n";

    return 0;
}
```