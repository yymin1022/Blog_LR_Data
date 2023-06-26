[문제 바로가기](https://boj.kr/20529)

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
        
        vector<string> mbti;
        for(int i = 0; i < N; i++){
            string input;
            cin >> input;
            mbti.push_back(input);
        }

        if(N > 32){
            cout << 0 << "\n";
            continue;
        }

        int ans = 2147483647;
        for(int i = 0; i < N; i++){
            for(int j = i + 1; j < N; j++){
                for(int k = j + 1; k < N; k++){
                    int tmp = 0;
                    for(int m = 0; m < 4; m++){
                        tmp += mbti[i][m] != mbti[j][m];
                        tmp += mbti[j][m] != mbti[k][m];
                        tmp += mbti[k][m] != mbti[i][m];
                    }
                    ans = min(tmp, ans);
                }
            }
        }

        cout << ans << "\n";
    }

    return 0;
}
```