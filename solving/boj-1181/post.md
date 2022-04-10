[문제 바로가기](https://boj.kr/1181)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<pair<int, string>> words;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        words.push_back(make_pair(input.size(), input));
    }

    sort(words.begin(), words.end());

    string before = "";
    for(int i = 0; i < N; i++){
        string current = words[i].second;
        if(current != before){
            cout << current << "\n";
            before = current;
        }
    }

    
    return 0;
}
```