[문제 바로가기](https://boj.kr/4344)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int C;
    cin >> C;

    while(C--){
        int N;
        cin >> N;

        int avg = 0;
        vector<int> score;
        for(int i = 0; i < N; i++){
            int input;
            cin >> input;
            score.push_back(input);
            avg += input;
        }

        avg /= N;
        float cnt = 0;
        for(int i = 0; i < N; i++){
            if(score[i] > avg){
                cnt += 1;
            }
        }

        cnt *= 100000;
        cnt /= N;

        cout << fixed;
        cout.precision(3);
        cout << round(cnt) / 1000 << "%\n";
    }

    return 0;
}
```