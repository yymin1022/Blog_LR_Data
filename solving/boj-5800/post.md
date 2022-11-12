[문제 바로가기](https://boj.kr/5800)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int K;
    cin >> K;

    for(int i = 1; i <= K; i++){
        cout << "Class " << i << "\n";

        int N;
        cin >> N;
        vector<int> score;
        for(int j = 0; j < N; j++){
            int input;
            cin >> input;
            score.push_back(input);
        }

        sort(score.begin(), score.end());

        int ans = 0;
        for(int j = 1; j < N; j++){
            ans = max(score[j] - score[j - 1], ans);
        }

        cout << "Max " << score[N - 1] << ", Min " << score[0] << ", Largest gap " << ans << "\n";
    }

    return 0;
}
```