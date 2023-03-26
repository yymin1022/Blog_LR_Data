[문제 바로가기](https://boj.kr/12018)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    vector<int> scores;
    for(int i = 0; i < N; i++){
        int P, L;
        cin >> P >> L;

        vector<int> tmp;
        for(int j = 0; j < P; j++){
            int input;
            cin >> input;
            tmp.push_back(input);
        }
        if(P < L){
            scores.push_back(1);
        }else{
            sort(tmp.begin(), tmp.end(), greater<int>());
            scores.push_back(tmp[L - 1]);
        }
    }

    sort(scores.begin(), scores.end());

    int ans = 0;
    for(int i = 0; i < N; i++){
        if(M < scores[i]){
            break;
        }
        M -= scores[i];
        ans++;
    }

    cout << ans << "\n";

    return 0;
}
```