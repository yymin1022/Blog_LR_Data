[문제 바로가기](https://boj.kr/9324)

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
        string M;
        cin >> M;

        int cnt[26];
        memset(cnt, 0, sizeof(cnt));

        bool isOK = true;
        for(int i = 0; i < M.size(); i++){
            cnt[M[i] - 65]++;
            if(cnt[M[i] - 65] == 3){
                if(i >= M.size() - 1 || M[i] != M[i + 1]){
                    isOK = false;
                    break;
                }

                i++;
                cnt[M[i] - 65] = 0;
            }
        }

        cout << (isOK ? "OK" : "FAKE") << "\n";
    }

    return 0;
}
```