[문제 바로가기](https://boj.kr/1358)

```c++
#include <bits/stdc++.h>

using namespace std;

bool checkInside(int, int);

int W, H, X, Y, P;

int main() {
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    cin >> W >> H >> X >> Y >> P;

    int answer = 0;
    for(int i = 0; i < P; i++){
        int pX, pY;
        cin >> pX >> pY;

        if(checkInside(pX, pY)){
            answer++;
        }
    }

    cout << answer << "\n";

    return 0;
}

bool checkInside(int pX, int pY){
    if((X <= pX && pX <= X + W) && (Y <= pY && pY <= Y + H)){
        return true;
    }else{
        int dist1 = (X - pX) * (X - pX) + (Y + H / 2 - pY) * (Y + H / 2 - pY);
        int dist2 = (X + W - pX) * (X + W - pX) + (Y + H / 2 - pY) * (Y + H / 2 - pY);

        if(dist1 <= H * H / 4 || dist2 <= H * H / 4){
            return true;
        }
    }

    return false;
}```