[문제 바로가기](https://boj.kr/11557)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    while(T--){
        int N;
        cin >> N;

        vector<pair<int, string>> alchol;
        for(int i = 0; i < N; i++){
            string S;
            int L;
            cin >> S >> L;
            alchol.push_back(make_pair(L, S));
        }

        sort(alchol.begin(), alchol.end(), greater<pair<int, string>>());

        cout << alchol[0].second << "\n";
    }

    return 0;
}
```