[문제 바로가기](https://boj.kr/1946)

```c++
#include <bits/stdc++.h>

using namespace std;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<pair<int, int>> score;
        for(int i = 0; i < N; i++){
            int x, y;
            cin >> x >> y;
            score.push_back(make_pair(x, y));
        }

        sort(score.begin(), score.end());

        int ans = 0;
        int min = N + 1;
        for(int i = 0; i < N; i++){
            if(score[i].second < min){
                ans++;
                min = score[i].second;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```