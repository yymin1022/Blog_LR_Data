[문제 바로가기](https://boj.kr/1764)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    set<string> notListen;
    vector<string> answer;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        notListen.insert(input);
    }

    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        if(notListen.find(input) != notListen.end()){
            answer.push_back(input);
        }
    }

    sort(answer.begin(), answer.end());

    cout << answer.size() << "\n";
    for(int i = 0; i < answer.size(); i++){
        cout << answer[i] << "\n";
    }

    return 0;
}
```