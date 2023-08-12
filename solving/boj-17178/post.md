[문제 바로가기](https://boj.kr/17178)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<char, int> A, pair<char, int> B){
    if(A.first == B.first){
        return A.second < B.second;
    }
    return A.first < B.first;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<char, int>> entire;
    vector<pair<char, int>> wait;
    for(int i = 0; i < N * 5; i++){
        string input;
        cin >> input;

        char a = input[0];
        int b = stoi(input.erase(0, 2));
        entire.push_back(make_pair(a, b));
        wait.push_back(make_pair(a, b));
    }

    sort(entire.begin(), entire.end(), cmp);

    int i = 0;
    int j = 0;
    stack<pair<char, int>> stk;
    while(i < N * 5 && j < N * 5){
        if(!stk.empty() && stk.top().first == entire[j].first && stk.top().second == entire[j].second){
            j++;
            stk.pop();
        }else if(entire[j].first == wait[i].first && entire[j].second == wait[i].second){
            i++;
            j++;
        }else{
            stk.push(wait[i]);
            i++;
        }
    }

    while(!stk.empty()){
        if(stk.top().first != entire[j].first || stk.top().second != entire[j].second){
            cout << "BAD" << "\n";
            return 0;
        }
        j++;
        stk.pop();
    }

    cout << "GOOD" << "\n";

    return 0;
}
```
