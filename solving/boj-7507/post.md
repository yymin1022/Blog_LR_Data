[문제 바로가기](https://boj.kr/7507)

```c++
#include  <bits/stdc++.h>

using namespace std;

typedef struct {
    int D;
    int S;
    int E;
} game;

bool cmp(game A, game B){
    if(A.D == B.D){
        return A.E < B.E;
    }else{
        return A.D < B.D;
    }
}

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int T;
    cin >> T;

    for(int t = 1; t <= T; t++){
        int N;
        cin >> N;

        vector<game> games;
        for(int i = 0; i < N; i++){
            int D, S, E;
            cin >> D >> S >> E;
            games.push_back({D, S, E});
        }

        sort(games.begin(), games.end(), cmp);

        int ans = 1;
        game prev = games[0];
        for(int i = 1; i < N; i++){
            if(games[i].D != prev.D || games[i].S >= prev.E){
                ans++;
                prev = games[i];
            }
        }

        cout << "Scenario #" << t << ":\n";
        cout << ans << "\n\n";
    }

    return 0;
}
```