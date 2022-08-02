[문제 바로가기](https://boj.kr/14503)

```c++
#include <bits/stdc++.h>

using namespace std;

int dx[4] = {-1, 0, 1, 0};
int dy[4] = {0, 1, 0, -1};
int house[51][51];

int main(void) {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    int r, c, d;
    cin >> r >> c >> d;

    for(int i = 0; i < N; i++){
        for(int j = 0; j < M; j++){
            cin >> house[i][j];
        }
    }

    int answer = 0;
    while(1){
        if(house[r][c] == 0){
            answer++;
            house[r][c] = 2;
        }        

        bool isCleaned = false;
        for(int i = 0; i < 4; i++){
            int nextD = (d + 3 - i) % 4;
            int nextR = r + dx[nextD];
            int nextC = c + dy[nextD];

            if(house[nextR][nextC] == 0){
                d = nextD;
                r = nextR;
                c = nextC;
                isCleaned = true;
                break;
            }
        }

        if(!isCleaned){
            int nextR = r + dx[(d + 2) % 4];
            int nextC = c + dy[(d + 2) % 4];

            if(house[nextR][nextC] == 1){
                break;
            }

            r = nextR;
            c = nextC;
        }
    }

    cout << answer << "\n";

    return 0;
}```