[문제 바로가기](https://boj.kr/2754)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    string score;
    cin >> score;

    cout << fixed;
    cout.precision(1);

    if(score[0] == 'F'){
        cout << 0.0 << "\n";
        return 0;
    }

    float answer = 69.0;
    answer -= (float)score[0];

    if(score[1] == '+'){
        answer += 0.3;
    }else if(score[1] == '-'){
        answer -= 0.3;
    }

    cout << answer << "\n";

    return 0;
}```