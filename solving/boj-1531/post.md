[문제 바로가기](https://boj.kr/1531)

```c++
#include  <bits/stdc++.h>

using namespace std;

int picture[101][101];

int main(){
    cin.tie(NULL);
    cout.tie(NULL);
    ios_base::sync_with_stdio(false);

    int N, M;
    cin >> N >> M;

    for(int i = 0; i < N; i++){
        int x1, y1, x2, y2;
        cin >> x1 >> y1 >> x2 >> y2;

        for(int j = x1; j <= x2; j++){
            for(int k = y1; k <= y2; k++){
                picture[j][k]++;
            }
        }
    }

    int ans = 0;
    for(int i = 1; i <= 100; i++){
        for(int j = 1; j <= 100; j++){
            if(picture[i][j] > M){
                ans++;
            }
        }
    }
    cout << ans << "\n";

    return 0;
}
```