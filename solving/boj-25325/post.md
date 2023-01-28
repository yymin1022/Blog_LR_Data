[문제 바로가기](https://boj.kr/25325)

```c++
#include <bits/stdc++.h>

using namespace std;

bool comp(pair<string, int> p1, pair<string, int> p2){
    if (p1.second == p2.second){
        return p1.first < p2.first;
    }
    return p1.second > p2.second;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    map<string, int> score;
    for(int i = 0; i < N; i++){
        string name;
        cin >> name;
        score[name] = 0;
    }

    cin.ignore();
    for(int i = 0; i < N; i++){
        string input;
        getline(cin, input);

        int j = 0;
        int idx = 0;
        while(true){
            if(input[j] == ' '){
                string name = input.substr(idx, j - idx);
                idx = j + 1;
                score[name]++;
            }else if(input[j] == '\0'){
                string name = input.substr(idx, j - idx);
                score[name]++;
                break;
            }
            j++;
        }
    }

    vector<pair<string, int>> data(score.begin(), score.end());
    sort(data.begin(), data.end(), comp);

    for(int i = 0; i < N; i++){
        cout << data[i].first << " " << data[i].second << "\n";
    }

    return 0;
}
```