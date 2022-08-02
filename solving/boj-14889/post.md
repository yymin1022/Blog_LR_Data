[문제 바로가기](https://boj.kr/14889)

```c++
#include <bits/stdc++.h>

using namespace std;

void solve(int, int);

bool isChecked[20];
int N;
int ans = 987654321;
int person[20][20];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> N;
    for(int i = 0; i < N; i++){
        for(int j = 0; j < N; j++){
            cin >> person[i][j];
        }
    }

    solve(0, 0);

    cout << ans << "\n";
    return 0;
}

void solve(int cnt, int idx) {
    if(idx == N){
        return;
    }

    if(cnt == N / 2){
        int sumStart = 0;
        int sumLink = 0;
        for(int i = 0; i < N; i++){
            for(int j = 0; j < N; j++){
                if(isChecked[i] && isChecked[j]){
                    sumStart += person[i][j];
                }

                if(!isChecked[i] && !isChecked[j]){
                    sumLink += person[i][j];
                }
            }
        }

        ans = min(ans, abs(sumStart - sumLink));
        return;
    }

    isChecked[idx] = true;
    solve(cnt + 1, idx + 1);

    isChecked[idx] = false;
    solve(cnt, idx + 1);
}```