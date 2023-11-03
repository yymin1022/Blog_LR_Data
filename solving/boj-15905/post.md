[문제 바로가기](https://boj.kr/15905)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<int, int> A, pair<int, int> B){
    if(A.first == B.first){
        return A.second < B.second;
    }
    return A.first > B.first;
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> student;
    for(int i = 0; i < N; i++){
        int score, penalty;
        cin >> score >> penalty;
        student.push_back(make_pair(score, penalty));
    }

    sort(student.begin(), student.end(), cmp);

    for(int i = 5; i <= N; i++){
        if(i == N || student[i].first != student[4].first){
            cout << i - 5 << "\n";
            return 0;
        }
    }

    return 0;
}
```