[문제 바로가기](https://boj.kr/1205)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, S, P;
    cin >> N >> S >> P;

    if(N == 0){
        cout << 1 << "\n";
        return 0;
    }

    vector<int> score;
    for(int i = 0; i < N; i++){
        int input;
        cin >> input;
        score.push_back(input);
    }

    int ans = 1;
    int cnt = 0;
    for(int i = 0; i < N; i++){
        if(S < score[i]){
            ans++;
        }else if(S > score[i]){
            break;
        }
        cnt++;
    }

    if(cnt == P){
        cout << -1 << "\n";
        return 0;
    }

    cout << ans << "\n";

    return 0;
}

```