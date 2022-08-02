[문제 바로가기](https://boj.kr/2492)

```c++
#include <iostream>
#include <algorithm>

using namespace std;

int main(){
    ios_base :: sync_with_stdio(false);
    cin.tie(NULL);
    cout.tie(NULL);

    int N, M, T, K;
    cin >> N >> M >> T >> K;

    int maxCount = 0;
    int maxX, maxY;

    pair<int, int> jewels[T];

    for(int i = 0; i < T; i++){
        int xT, yT;
        cin >> xT >> yT;

        jewels[i] = make_pair(xT, yT);
    }

    sort(jewels, jewels + T);

    for(int i = 0; i < T; i++){
        int maxTX = 0;
        for(int j = 0; j < T; j++){
            if(jewels[j].first - jewels[i].first <= K){
                maxTX++;
            }
        }

        int y[T];
        for(int j = 0; j < maxTX - i; j++){
            y[j] = jewels[j + i].second;
        }

        sort(y, y + maxTX - i);

        for(int X = 0; X < maxTX - i; X++){
            int maxTY = 0;
            for(int Y = 0; Y < maxTX - i; Y++){
                if(y[Y] - y[X] <= K){
                    maxTY++;
                }
            }

            if(maxCount < maxTY - X){
                maxCount = maxTY - X;
                maxX = min(N, jewels[i].first + K) - K;
                maxY = min(M, y[X] + K);
            }
        }
    }

    cout << maxX << " " << maxY << "\n";
    cout << maxCount << "\n";

    return 0;
}```