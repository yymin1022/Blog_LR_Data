[문제 바로가기](https://boj.kr/7568)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, int>> person;
    for(int i = 0; i < N; i++){
        int x, y;
        cin >> x >> y;

        person.push_back(make_pair(x, y));
    }

    vector<int> rank(N, 1);
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            if(i != j){
                if(person[i].first > person[j].first && person[i].second > person[j].second){
                    rank[j]++;
                }
            }
        }
    }

    for(int i = 0; i < N; i++){
        cout << rank[i] << " ";
    }
    
    return 0;
}
```