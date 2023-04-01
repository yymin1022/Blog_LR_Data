[문제 바로가기](https://boj.kr/15702)

```c++
#include <bits/stdc++.h>

using namespace std;

bool comp(pair<int, int> stuA, pair<int, int> stuB){
    if(stuA.second == stuB.second){
        return stuA.first < stuB.first;
    }
    return stuA.second > stuB.second;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> score;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        score.push_back(input);
    }

    vector<pair<int, int>> student;
    for(int i = 0; i < M; i++){
        int id;
        cin >> id;

        student.push_back(make_pair(id, 0));
        for(int j = 0; j < N; j++){
            char input;
            cin >> input;

            if(input == 'O'){
                student[i].second += score[j];
            }
        }
    }

    sort(student.begin(), student.end(), comp);

    cout << student[0].first << " ";
    cout << student[0].second << "\n";

    return 0;
}
```