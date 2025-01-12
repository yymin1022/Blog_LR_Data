[문제 바로가기](https://boj.kr/20113)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    vector<int> vote(N + 1, 0);
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;

        if(input != 0){
            vote[input]++;
        }
    }

    int ansIdx;
    int ansVal = 0;
    for(int i = 1; i <= N; i++){
        if(vote[i] > ansVal){
            ansIdx = i;
            ansVal = vote[i];
        }
    }

    for(int i = 1; i <= N; i++){
        if(i != ansIdx && vote[i] == ansVal){
            cout << "skipped" << "\n";
            return 0;
        }
    }

    cout << ansIdx << "\n";

    return 0;
}
```
