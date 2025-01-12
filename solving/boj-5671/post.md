[문제 바로가기](https://boj.kr/5671)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    while(cin >> N >> M){
        int ans = 0;
        for(int i = N; i <= M; i++){
            string tmp = to_string(i);

            vector<int> cnt(10,0);
            for(int i = 0; i < tmp.size(); i++){
                cnt[tmp[i] - '0']++;
            }

            bool flag = true;
            for(int i = 0; i < 10; i++){
                if(cnt[i] >= 2){
                    flag = false;
                    break;
                }
            }

            if(flag){
                ans++;
            }
        }

        cout << ans << "\n";
    }

    return 0;
}

```