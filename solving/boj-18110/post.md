[문제 바로가기](https://boj.kr/18110)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;

    if(!N){
        cout << 0 << "\n";
        return 0;
    }

    deque<int> score;
    for(int i = 0; i < N; i++) {
        int input;
        cin >> input;
        score.push_back(input);
    }

    sort(score.begin(), score.end());

    double offset = round(N * 0.15);
    int sum = 0;
    for(int i = offset; i < N - offset; i++){
        sum += score[i];
    }

    cout << round(sum / (N - offset * 2)) << "\n";

    return 0;
}
```