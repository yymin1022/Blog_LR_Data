[문제 바로가기](https://boj.kr/5523)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    pair<int, int> score = make_pair(0, 0);
    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;

        if(A > B){
            score.first++;
        }else if(A < B){
            score.second++;
        }
    }

    cout << score.first << " ";
    cout << score.second << "\n";

    return 0;
}
```
