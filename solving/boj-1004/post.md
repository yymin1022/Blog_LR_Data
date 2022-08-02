[문제 바로가기](https://boj.kr/1004)

```c++
#include <bits/stdc++.h>

using namespace std;

bool isInside(int, int, int, int, int);


int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N, T;
    cin >> T;
    while(T--){
        int answer = 0;
        int x1, y1, x2, y2;
        cin >> x1 >> y1 >> x2 >> y2;
        cin >> N;
        while(N--){
            int x, y, r;
            cin >> x >> y >> r;
            
            bool isStartInside = isInside(x1, y1, x, y, r);
            bool isEndInside = isInside(x2, y2, x, y, r);

            if(isStartInside ^ isEndInside){
                answer++;
            }
        }

        cout << answer << "\n";
    }
}

bool isInside(int pointX, int pointY, int planetX, int planetY, int planetR){
    int distance = (pointX - planetX) * (pointX - planetX) + (pointY - planetY) * (pointY - planetY);
    if(distance < planetR * planetR){
        return true;
    }

    return false;
}```