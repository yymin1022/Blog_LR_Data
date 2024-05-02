[문제 바로가기](https://boj.kr/20365)

```c++
#include  <bits/stdc++.h>

using namespace std;

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N;
    string S;
    cin >> N >> S;

    int ans = N;
    int tmp = 1;
    for(int i = 0; i < N;){
        if(S[i] == 'B'){
            i++;
            continue;
        }
        tmp++;

        while(true){
            if(i >= N){
                break;
            }

            if(S[i] == 'B'){
                break;
            }
            i++;
        }
    }

    ans = min(ans, tmp);

    tmp = 1;
    for(int i = 0; i < N;){
        if(S[i] == 'R'){
            i++;
            continue;
        }
        tmp++;

        while(true){
            if(i >= N){
                break;
            }

            if(S[i] == 'R'){
                break;
            }
            i++;
        }
    }

    ans = min(ans, tmp);
    cout << ans << "\n";

    return 0;
}

```