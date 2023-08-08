[문제 바로가기](https://boj.kr/1969)

```c++
#include <bits/stdc++.h>

using namespace std;

int cnt[51][4];

int main() {
    cin.tie(0);
    cout.tie(0);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        string input;
        cin >> input;

        for(int j = 0; j < M; j++){
            if(input[j] == 'A'){
                cnt[j][0]++;
            }else if(input[j] == 'C'){
                cnt[j][1]++;
            }else if(input[j] == 'G'){
                cnt[j][2]++;
            }else{
                cnt[j][3]++;
            }
        }
    }

    string ans = "";
    int sum = 0;
    for(int i = 0; i < M; i++){
        int maxCnt = 0;
        int maxIdx = 0;
        for(int j = 0; j < 4; j++){
            if(cnt[i][j] > maxCnt){
                maxCnt = cnt[i][j];
                maxIdx = j;
            }
        }

        char tmp[4] = {'A', 'C', 'G', 'T'};
        ans += tmp[maxIdx];
        sum += N - maxCnt;
    }

    cout << ans << "\n";
    cout << sum << "\n";

    return 0;
}
```