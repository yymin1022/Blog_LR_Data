[문제 바로가기](https://boj.kr/6146)

```c++
#include <bits/stdc++.h>

using namespace std;

int arr[1001][1001];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int X, Y, N;
    cin >> X >> Y >> N;
    X += 500;
    Y += 500;

    for(int i = 0; i < N; i++){
        int A, B;
        cin >> A >> B;
        arr[A + 500][B + 500] = 2;
    }

    queue<pair<int, int>> bfsQ;
    bfsQ.push(make_pair(500, 500));
    arr[500][500] = 1;

    while(!bfsQ.empty()){
        int curX = bfsQ.front().first;
        int curY = bfsQ.front().second;
        bfsQ.pop();

        if(curX == X && curY == Y){
            cout << arr[curX][curY] - 1 << "\n";
            return 0;
        }

        int dx[4] = {0, 1, 0, -1};
        int dy[4] = {1, 0, -1, 0};
        for(int i = 0; i < 4; i++){
            int newX = curX + dx[i];
            int newY = curY + dy[i];

            if(newX < 0 || newX >= 1001 || newY < 0 || newY >= 1001 || arr[newX][newY] > 0){
                continue;
            }

            arr[newX][newY] = arr[curX][curY] + 1;
            bfsQ.push(make_pair(newX, newY));
        }
    }

    return 0;
}
```
