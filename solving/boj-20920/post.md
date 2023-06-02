[문제 바로가기](https://boj.kr/20920)

```c++
#include <bits/stdc++.h>

using namespace std;

bool cmp(pair<string, int> A, pair<string, int> B){
    if(A.second != B.second){
        return A.second > B.second;
    }

    if(A.first.size() != B.first.size()){
        return A.first.size() > B.first.size();
    }

    return A.first < B.first;
}

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    map<string, int> words;
    for(int i = 0; i < N; i++){
        string word;
        cin >> word;

        if(word.size() >= M) {
            words[word]++;
        }
    }

    vector<pair<string, int>> arr;
    for(auto iter = words.begin(); iter != words.end(); iter++){
        arr.push_back(make_pair(iter->first, iter->second));
    }

    sort(arr.begin(), arr.end(), cmp);

    for(int i = 0; i < arr.size(); i++){
        cout << arr[i].first << "\n";
    }

    return 0;
}
```