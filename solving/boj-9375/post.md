[문제 바로가기](https://boj.kr/9375)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;
    for(int i = 0; i < T; i++){
        int N;
        cin >> N;

        map<string, int> fashion;
        for(int j = 0; j < N; j++){
            string name, type;
            cin >> name >> type;
            fashion[type]++;
        }

        int answer = 1;
        for(auto j = fashion.begin(); j != fashion.end(); j++){
            answer *= j->second + 1;
        }

        cout << answer - 1 << "\n";
    }

    return 0;
}
```