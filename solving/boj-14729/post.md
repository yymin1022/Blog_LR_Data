[문제 바로가기](https://boj.kr/14729)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);
    
    int N;
    cin >> N;

    vector<double> score;
    for(int i = 0; i < N; i++){
        double input;
        cin >> input;

        score.push_back(input);
    }

    sort(score.begin(), score.end());

    cout << fixed;
    cout.precision(3);

    for(int i = 0; i < 7; i++){
        cout << score[i] << "\n";
    }

    return 0;
}
```