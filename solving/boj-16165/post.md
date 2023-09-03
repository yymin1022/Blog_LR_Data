[문제 바로가기](https://boj.kr/16165)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<pair<string, vector<string>>> groups;
    for(int i = 0; i < N; i++){
        string name;
        int cnt;
        cin >> name >> cnt;

        groups.push_back(make_pair(name, vector<string>()));
        for(int j = 0; j < cnt; j++){
            cin >> name;
            groups[i].second.push_back(name);
        }
        sort(groups[i].second.begin(), groups[i].second.end());
    }

    for(int i = 0; i < M; i++){
        string name;
        int cmd;
        cin >> name >> cmd;

        if(cmd == 0){
            for(int j = 0; j < N; j++){
                if(groups[j].first == name){
                    for(int k = 0; k < groups[j].second.size(); k++){
                        cout << groups[j].second[k] << "\n";
                    }
                    break;
                }
            }
        }else{
            for(int j = 0; j < N; j++){
                for(int k = 0; k < groups[j].second.size(); k++){
                    if(groups[j].second[k] == name){
                        cout << groups[j].first << "\n";
                        break;
                    }
                }
            }
        }
    }

    return 0;
}```