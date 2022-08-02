[문제 바로가기](https://boj.kr/10814)

```c++
#include <bits/stdc++.h>

using namespace std;

bool compare(pair<int, string> one, pair<int, string> two){
    return one.first < two.first;
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, string>> person;
    for(int i = 0; i < N; i++){
        int age;
        string name;
        cin >> age >> name;

        person.push_back(make_pair(age, name));
    }

    stable_sort(person.begin(), person.end(), compare);

    for(int i = 0; i < N; i++){
        cout << person[i].first << " " << person[i].second << "\n";
    }
    
    return 0;
}```