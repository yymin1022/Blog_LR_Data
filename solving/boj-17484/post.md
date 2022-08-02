[문제 바로가기](https://boj.kr/17484)

```c++
#include <bits/stdc++.h>

using namespace std;

int dp(int, int, int);

int N, M;
int dx[3] = {-1, 0, 1};
int space[10][10];

int main(){
    cin.tie(0);
    cout.tie(0);
    ios::sync_with_stdio(false);

    cin >> N >> M;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> space[j][i];
        }
    }

    int ans = 987654321;
    for(int i = 0; i < M; i++){
        ans = min(dp(i, 0, -1), ans);
    }

    cout << ans << "\n";

    return 0;
}

int dp(int curX, int curY, int from){
    if(curY == N){
        return 0;
    }

    int val = 987654321;
    for(int i = 0; i < 3; i++){
        if(from == i){
            continue;
        }
        
        int newX = curX + dx[i];
        if(newX < 0 || newX >= M){
            continue;
        }

        val = min(dp(newX, curY + 1, i) + space[curX][curY], val);
    }

    return val;
}```