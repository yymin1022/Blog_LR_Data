[문제 바로가기](https://boj.kr/12891)

```c++
#include <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    string S;
    cin >> N >> M >> S;

    vector<int> must(4, 0);
    cin >> must[0] >> must[1] >> must[2] >> must[3];

    vector<int> cnt(4, 0);
    for(int i = 0; i < M; i++){
        if(S[i] == 'A'){
            cnt[0]++;
        }else if(S[i] == 'C'){
            cnt[1]++;
        }else if(S[i] == 'G'){
            cnt[2]++;
        }else if(S[i] == 'T'){
            cnt[3]++;
        }
    }

    bool flag = true;
    for(int j = 0; j < 4; j++){
        if(cnt[j] < must[j]){
            flag = false;
            break;
        }
    }

    int ans = 0;
    if(flag){
        ans++;
    }

    for(int i = 0; i < N - M; i++){
        if(S[i] == 'A'){
            cnt[0]--;
        }else if(S[i] == 'C'){
            cnt[1]--;
        }else if(S[i] == 'G'){
            cnt[2]--;
        }else if(S[i] == 'T'){
            cnt[3]--;
        }

        if(S[i + M] == 'A'){
            cnt[0]++;
        }else if(S[i + M] == 'C'){
            cnt[1]++;
        }else if(S[i + M] == 'G'){
            cnt[2]++;
        }else if(S[i + M] == 'T'){
            cnt[3]++;
        }

        flag = true;
        for(int j = 0; j < 4; j++){
            if(cnt[j] < must[j]){
                flag = false;
                break;
            }
        }

        if(flag){
            ans++;
        }
    }

    cout << ans << "\n";

    return 0;
}

```