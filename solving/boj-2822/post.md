[문제 바로가기](https://boj.kr/2822)

```c++
#include <bits/stdc++.h>

using namespace std;

bool comp(pair<int, int> a, pair<int, int> b){
    return a.second > b.second;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    vector<pair<int, int>> score;
    for(int i = 1; i <= 8; i++){
        int input;
        cin >> input;
        score.push_back(make_pair(i, input));
    }

    sort(score.begin(), score.end(), comp);

    int sum = 0;
    for(int i = 0; i < 5; i++){
        sum += score[i].second;
    }

    cout << sum << "\n";

    vector<int> problem;
    for(int i = 0; i < 5; i++){
        problem.push_back(score[i].first);
    }

    sort(problem.begin(), problem.end());

    for(int i = 0; i < 5; i++){
        cout << problem[i] << " ";
    }

    return 0;
}
```