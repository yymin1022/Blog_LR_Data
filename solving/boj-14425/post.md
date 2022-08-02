[문제 바로가기](https://boj.kr/14425)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    set<string> S;
    for(int i = 0; i < N; i++){
        string input;
        cin >> input;
        S.insert(input);
    }

    int cnt = 0;
    for(int i = 0; i < M; i++){
        string input;
        cin >> input;

        if(S.find(input) != S.end()){
            cnt++;
        }
    }

    cout << cnt << "\n";

    return 0;
}```