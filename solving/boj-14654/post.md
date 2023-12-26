[문제 바로가기](https://boj.kr/14654)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N;
    cin >> N;
    
    vector<int> game[2];
    for(int i = 0; i < N * 2; i++){
        int input;
        cin >> input;
        game[i / N].push_back(input);
    }

    int ans = 0;
    int cnt[2] = {0, 0};
    for(int i = 0; i < N; i++){
        if(game[0][i] == 1){
            if(game[1][i] == 2){
                cnt[0] = 0;
                cnt[1]++;
            }else if(game[1][i] == 3){
                cnt[0]++;
                cnt[1] = 0;
            }else{
                if(cnt[0] == 0){
                    cnt[0]++;
                    cnt[1] = 0;
                }else{
                    cnt[0] = 0;
                    cnt[1]++;
                }
            }
        }else if(game[0][i] == 2){
            if(game[1][i] == 1){
                cnt[0]++;
                cnt[1] = 0;
            }else if(game[1][i] == 3){
                cnt[0] = 0;
                cnt[1]++;
            }else{
                if(cnt[0] == 0){
                    cnt[0]++;
                    cnt[1] = 0;
                }else{
                    cnt[0] = 0;
                    cnt[1]++;
                }
            }
        }else{
            if(game[1][i] == 1){
                cnt[0] = 0;
                cnt[1]++;
            }else if(game[1][i] == 2){
                cnt[0]++;
                cnt[1] = 0;
            }else{
                if(cnt[0] == 0){
                    cnt[0]++;
                    cnt[1] = 0;
                }else{
                    cnt[0] = 0;
                    cnt[1]++;
                }
            }
        }

        ans = max(max(cnt[0], cnt[1]), ans);
    }

    cout << ans << "\n";

    return 0;
}
```