[문제 바로가기](https://boj.kr/22233)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N, M;
    cin >> N >> M;

    set<string> words;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        words.insert(input);
    }

    int cnt = N;
    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        string tmp = "";
        for(int j = 0; j < input.size(); j++){
            if(input[j] == ','){
                if(words.find(tmp) != words.end()){
                    words.erase(words.find(tmp));
                    cnt--;
                }
                tmp = "";
            }else{
                tmp.push_back(input[j]);
            }
        }
        if(words.find(tmp) != words.end()){
            words.erase(words.find(tmp));
            cnt--;
        }

        cout << cnt << "\n";
    }

    return 0;
}
```