[문제 바로가기](https://boj.kr/11292)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<string, double> A, pair<string, double> B){
    return A.second > B.second;
}

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    while(true){
        int N;
        cin >> N;

        if(!N)
            break;

        vector<pair<string, double>> person;
        for(int i = 0; i < N; i++){
            string name;
            double size;
            cin >> name >> size;
            person.push_back(make_pair(name, size));
        }

        sort(person.begin(), person.end(), cmp);

        for(int i = 0; i < N; i++){
            if(person[i].second == person[0].second){
                cout << person[i].first << " ";
            }
        }
        cout << "\n";
    }

    return 0;
}
```